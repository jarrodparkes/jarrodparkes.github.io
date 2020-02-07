---
layout: post
title:  GitHub Push to Tweet
date:   2017-10-01 
tags:   swift, serverless, bluemix, javascript, github, twitter
---

Yesterday I attended the Swift Cloud Workshop 2 in Austin, TX. The one-day conference was focused on discussing how Swift can be used outside of the Apple ecosystem. [Belinda Vennam](https://twitter.com/BeeMarieV), one of the keynote speakers, discussed how Swift code can be run on [Bluemix](http://bluemix.net/) in a "serverless" fashion. So, I had to try it myself. This short blog post discusses how to use [IBM's Cloud Functions](https://www.ibm.com/cloud-computing/bluemix/openwhisk) to post a tweet in response to a GitHub push event.

~

There are three high-level steps required to automate a tweet after a GitHub push:

1. TRIGGER: I commit/push to a GitHub repository
2. ACTION: Serverless function extracts commit message from the push
3. ACTION: Serverless function posts message to twitter

The trigger and actions mentioned above can be created using the [Bluemix CLI](https://console.bluemix.net/openwhisk/learn/cli) or web interface.

## Create the Trigger

With the web interface, I created the initial GitHub trigger; this required creating a GitHub access token, clicking through their trigger-creation wizard, and tweaking some settings.

## Write the First Action

Next, I wrote my first serverless function (called an action) in Swift. Here's the code:

```swift
// Cloud function accepts and returns a dictionary
func main(args: [String:Any]) -> [String:Any] {

    // Extract commit message (commits[0] --> message)
    guard let commits = args["commits"] as? [[String:Any]],
        let message = commits[0]["message"] as? String else {
        return [
            "success": false,
            "message": "could not find message in \(args)"
        ]
    }

    // Send message to next action
    return [
        "success": true,
        "message": "updated jarrodparkes.com: \(message)"
    ]
}
```

`main` is the entry point, and it accepts a dictionary of values called `args`. In this case, `args` contains values associated with a GitHub push like the commit message. Assuming the commit message exists, it is extracted and a dictionary is returned with a modified message; the dictionary acts as input to the section action.

## Write the Second Action

The second action was more difficult to create. I wasn't able to locate a Swift package for posting to Twitter, but I did find a repository with a working Node/Javascript example — [https://github.com/StrongLoop-Evangelists/openwhisk-twitterbot-template](https://github.com/StrongLoop-Evangelists/openwhisk-twitterbot-template). This repo contained more functionality than I needed, so with a few small adjustments, I created my own `main` function:

```javascript
const Twitter = require('twitter');
const request = require('request');

function main(args) {

	return new Promise( (resolve, reject) => {

		let client = new Twitter(require('./config.js'));		

		if (args.success == true) {
			client.post('statuses/update', {status: args.message}, function(err, tweet, response) {
	            if(err) reject(err);
	            resolve({result:tweet});
	        });
		} else {
			reject("Function to parse message from commit failed.")
		}
	});
}

exports.main = main;
```

This code is available on GitHub at [https://github.com/jarrodparkes/openwhisk-to-twitter](https://github.com/jarrodparkes/openwhisk-to-twitter). Because it requires dependencies, I couldn't create it in the Bluemix web interface. Instead, I had to bundle the code and its dependencies in a zip file, and post it to Bluemix using their CLI. This roughly translates to...

```bash
# navigate to repo
~ $ cd openwhisk-to-twitter

# install dependencies
~/openwhisk-to-twitter $ npm install

# archive code and dependencies
~/openwhisk-to-twitter $ zip -r -X "post-to-twitter.zip" *

# create new serverless function (action)
~/openwhisk-to-twitter $ bx wsk action create post-to-twitter --kind nodejs:6 post-to-twitter.zip
```

> **Note**: Bluemix has their own example of "packaging an action". Here's the [link](https://console.bluemix.net/docs/openwhisk/openwhisk_actions.html#openwhisk_actions).

## Final Steps

Once both actions were created, I wired them together as a sequence. Then, I set the GitHub trigger to invoke the sequence. That's it :)!
