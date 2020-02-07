---
layout: post
title:  Mock Objects for Testing
date:   2017-08-30 
tags:   testing, swift
---

[Mocking](https://en.wikipedia.org/wiki/Mock_object), or using "mock objects", is essential to unit testing. I've seen it applied at least three times in the last two weeks. It's usefulness can be distilled to the fact that it gives you tight control over the code path. With a mock object you can force your testing code to be right, but more importantly, _to be wrong_. Mock objects also give you the ability to circumvent dependencies and waits. For example, my mocking Swift's `URLSession` you can write unit tests where you can assume the networking code executes successfully — this lets you focus on the code you care about testing.

Here are some valuable introductions on the topic:

- [WWDC 2017: Engineering for Testability](https://developer.apple.com/videos/play/wwdc2017/414/) by Apple
- [Mocking Classes You Don't Own](http://masilotti.com/testing-nsurlsession-input/) by Joe Masilotti
