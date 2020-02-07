---
layout: post
title:  Google App Script to Twitter
date:   2017-07-31 07:03:00
tags:   google, javascript, twitter
---

Recently, a work task compelled me to connect a Google App Script (GAS script) to Twitter. Upon searching, I found existing tutorials on the matter, but most of them were rendered obsolete because of a depreciated OAuth library. Digging deeper, I discovered new Google tutorials, and I was able to piece together a workable solution. Assuming you know [how to create a GAS script](https://developers.google.com/apps-script/guides/docs), here is what you need...

- [Create a Twitter App](https://apps.twitter.com/)
- [Get Consumer Keys and Access Tokens for App](http://chimpgroup.com/knowledgebase/twitter-api-keys/)
- Create GAS script, with the following files...

**Twitter.gs**

```javascript
var TWITTER_CONSUMER_KEY = "<<TWITTER_CONSUMER_KEY>>";
var TWITTER_CONSUMER_SECRET = "<<TWITTER_CONSUMER_SECRET>>";
var TWITTER_ACCESS_TOKEN = "<<TWITTER_ACCESS_TOKEN>>";
var TWITTER_ACCESS_SECRET = "<<TWITTER_ACCESS_SECRET>>";

/**
 * Sends a tweet.
 * @param {String} msg - the message to send
 */
function sendTweet(tweet) {
  if (typeof OAuth1 === 'undefined') {
    var libUrl = 'https://developers.google.com/adwords/scripts/docs/examples/oauth10-library';
    throw Error('OAuth1 library not found. Please take a copy of the OAuth1 ' +
        'library from ' + libUrl + ' and append to the bottom of this script.');
  }
  var params = '';
  var status = tweet.substring(0, 160);
  var options = {method: 'POST', payload: {status: status}};
  var authUrlFetch = OAuth1.withAccessToken(TWITTER_CONSUMER_KEY, TWITTER_CONSUMER_SECRET,
      TWITTER_ACCESS_TOKEN, TWITTER_ACCESS_SECRET);
  var response = authUrlFetch
      .fetch('https://api.twitter.com/1.1/statuses/update.json', params,
      options);
  var responseText = response.getContentText();

  // The complex response object with the status of the send request. See https://dev.twitter.com/rest/reference/post/statuses/update.
  return JSON.parse(responseText);
}
```

**OAuth.gs**

```javascript
// Copy/paste contents from https://developers.google.com/adwords/scripts/docs/examples/oauth10-library
```

**Code.gs**

```javascript
function main() {
  sendTweet('this is a test tweet! #googleappscript');
}
```

And that's it!
