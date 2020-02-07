---
layout: post
title:  Measuring App Performance with Logging
date:   2019-03-06 
tags:   ios
---

I watched an awesome [WWDC video on measuring performance with logging](https://developer.apple.com/videos/play/wwdc2018/405/) this week, and I wanted to make sure I captured a few notes:

- `os_signpost` can be used to measure performance
- use "start" and "end" calls to denote the work you want measured
- `os_signpost` calls can include a category, metadata, and ID so that work can be traced regardless of whether it is a sync or async task
- you can also generate signpost events (called "points of interest") to track when something occurs during a measured interval (ex: "started download", "downloaded first/second/... image", and "finished download")
- `os_signpost` use a log handle; you can disable/enable a log handle during initialization; disabled signpost calls essentially become a NOOP's
- when using the signpost profiling instrument, you can set the recording to a windowed mode so that you’re only collecting/caring about the last X minutes of signpost data
- "points of interest" can be used like event logging in Firebase or anything else
- you can create a custom profile/instrument so that you can shape the signpost data in a way which is most useful to you
