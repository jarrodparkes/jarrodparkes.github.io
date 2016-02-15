---
layout: post
title:  Making a Network Request
date:   2015-11-02 19:17:58-0600
tags:   swift
---

Tonight let&#39;s talk about making network requests in Swift. You can make a request directly from a [unified resource location (URL)](https://en.wikipedia.org/wiki/Uniform_Resource_Locator), but it is better to first construct a valid request object. There are two options for request objects: `NSURLRequest` or `NSMutableURLRequest`. A `NSMutableURLRequest` provides many more configuration options that a `NSURLRequest`, but we'll keep it simple and use a `NSURLRequest`:

```swift
import Foundation

let networkRequest = NSURLRequest(URL:
    NSURL(string: "http://gturnquist-quoters.cfapps.io/api/random")!)
```

**Note: You'll need to `import Foundation` in order to use the `NSURLRequest` and other objects used in this example.**

When we create a `NSURLRequest`, we can specifying the URL where the request will be made. Unlike a URL for a basic web page, this URL returns random JSON data. If you attempt to visit the above URL in your browser, you should see JSON like the following:

```json
{
    "type": "success",
    "value": {
        "id": 6,
        "quote": "It embraces convention over 
        configuration, providing an experience on par 
        with frameworks that excel at early stage 
        development, such as Ruby on Rails."
    }
}
```

This JSON can be consumed by an app to do something useful. But, to gain access to this data, we need to download it from its network location. At this point, all we've done is create an object that represents the request we want to make. To actually perform the request, we must initialize and start a network task using Swift's `NSURLSession` API.

[From Apple's documentation](https://developer.apple.com/library/ios/documentation/Foundation/Reference/NSURLSession_class/#//apple_ref/occ/clm/NSURLSession/sharedSession), we read that `NSURLSession` gives us the ability to perform network requests (downloads):

> `NSURLSession`... gives your app the ability to perform background downloads when your app is not running or, in iOS, while your app is suspended.

The `dataTaskWithRequest` (that takes a completion handler) method is the one we want to use because it can take our request object as a parameter and create a network task. To call the method, we must use a `NSURLSession` object. But, don't worry, we can use the shared `NSURLSession` object provided by the `sharedSession` class method.

```swift
let task = NSURLSession.sharedSession().dataTaskWithRequest(
    networkRequest) { (data, response, error) in
    // do something with the response
}
task.resume()
```   

This first part of this snippet creates the network task. Then, after we've created the task we must call its `resume` method to start the task. You'll also notice the `dataTaskWithRequest:completionHandler:` takes a trailing closure with three parameters:

<table>
    <thead>
        <tr>
            <th>Parameter</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>data</td>
            <td>NSData?</td>
            <td>The data returned by the server.</td>
        </tr>
        <tr>
            <td>response</td>
            <td>NSURLResponse?</td>
            <td>An object that provides response metadata, such as HTTP headers and status code. If you are making an HTTP or HTTPS request, the returned object is actually an NSHTTPURLResponse object.</td>
        </tr>
        <tr>
            <td>error</td>
            <td>NSError?</td>
            <td>An error object that indicates why the request failed, or nil if the request was successful.</td>
        </tr>
    </tbody>
</table>

If the request completes successfully, then the error parameter will be nil. Otherwise, the data parameter is nil and the error parameter will contain information about the failure. So, we'll want to check for an error as soon as the closure is invoked: 

```swift
let task = NSURLSession.sharedSession().dataTaskWithRequest(
    networkRequest) { (data, response, error) in
    
    if error == nil {
        // do something with the data 
    }
}
task.resume()
```

In my networking course, we also check the HTTP status code before accessing any data; however, this is not always necessary. As soon as we know that no error is returned, we just need to write a little more code to convert the data (remember it is represented as a `NSData?` object) into something more usable:

```swift
let task = NSURLSession.sharedSession().dataTaskWithRequest(
    networkRequest) { (data, response, error) in
        
    if error == nil {
        
        /* 1 */
        var parsedResult: AnyObject? = nil
        do {
            parsedResult = try NSJSONSerialization.JSONObjectWithData(
                data!, options: .AllowFragments)
        } catch {
            print("Error")
        }
        
        /* 2 */
        print(parsedResult!)
    }
}
task.resume()
```

1. Here we've defined an `AnyObject` optional to store the result of converting the data returned by the request. The `JSONObjectWithData(_:options:)` method will return either a `NSDictionary` or `NSArray` which is why we've used `AnyObject?` to handle either.
2. Then, assuming no error is encountered, we print the data in its converted form.

Here is the full code example if you'd like to test it in a Playground. I've included the `import XCPlayground` and `needsIndefiniteExecution` setting so that the Playground executes indefinately and can complete the network request.

```swift
import Foundation
import XCPlayground

let networkRequest = NSURLRequest(URL:
    NSURL(string: "http://gturnquist-quoters.cfapps.io/api/random")!)

let task = NSURLSession.sharedSession().dataTaskWithRequest(
    networkRequest) { (data, response, error) in
    
    if error == nil {
                
        var parsedResult: AnyObject? = nil
        do {
            parsedResult = try NSJSONSerialization.JSONObjectWithData(
                data!, options: .AllowFragments)
        } catch {
            print("Error")
        }
                
        print(parsedResult!)
    }
}
task.resume()

XCPlaygroundPage.currentPage.needsIndefiniteExecution = true
```

Enjoy :)!
