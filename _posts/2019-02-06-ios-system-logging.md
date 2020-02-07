---
layout: post
title:  iOS System Logging
date:   2019-02-06 
tags:   ios
---

I've recently been learning how to use system logging on iOS. I have never needed this type of logging before because most bugs I encountered could be solved with a debugging session, Xcode, and a few carefully placed breakpoints; however, a recent bug presented an interesting problem: it could not be reproduced during any debug sessions, and it only appeared after letting the app run overnight while receiving remote push notifications. So what is a developer to do?

As of 2016, Apple has recommended using their new unified (system) logging system. You can learn plenty about it in their WWDC 22016 talk called [Unified Logging and Activity Tracing](https://developer.apple.com/videos/play/wwdc2016/721/). In a nutshell, iOS keeps a system log, and any application can write to it. Because this system log is an "open book", it can become quite cluttered and lengthy. But do not fear! Apple specially designed their new system log to use a compact binary format which can only be read by the macOS Console app — I'm being half-way sarcastic; of course, Apple made their own proprietary format that only their software can use.

Roughly speaking, here's how Apple recommends you use the unified logging in Swift:

```swift
import os

let log = OSLog(subsystem: "com.mydomain.myapp", category: "My Category")

os_log("%{public}@", log: log, type: .default, "a public message")
```

_[Apple's main documentation for the unified logging](https://developer.apple.com/documentation/os/logging)._

Most of this code is easy to parse, but I needed a refresher on the C-style printf substitution and the new idea of Parameter Privacy (public/private strings) — which is useful for protecting user's private data. You can read more about C-style strings in [Apple's String Programming Guide](https://developer.apple.com/library/archive/documentation/Cocoa/Conceptual/Strings/Articles/formatSpecifiers.html); Apple's explanation of Parameter Privacy starts [around 28:54 in the WWDC talk mentioned above](https://developer.apple.com/videos/play/wwdc2016/721/?time=1734).

Once the `os_log` statement is executed at runtime, the message will be added to the system log. There are two ways to view a system log:

1. You can view a system log in real-time by connecting your device to Xcode and going to the **Window --> Devices and Simulators** tab, selecting your device, and opening console
2. You can export a system log from your device. [Jesse Squires has a nice write-up on how to do this](https://www.jessesquires.com/blog/how-to-sysdiagnose-ios/).

In the Console app, you can filter messages by subsystem or category by adding the proper queries in the search bar:

![ios-system-logging]({{ site.url }}/images/ios-system-logging.png "Console app filtering")

And Viola!
