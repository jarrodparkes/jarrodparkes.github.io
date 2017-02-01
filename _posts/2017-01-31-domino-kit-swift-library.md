---
layout: post
title:  DominoKit Swift Library
date:   2017-01-31 11:37:00-0600
tags:
---

![Domino Kit Icon](https://raw.githubusercontent.com/jarrodparkes/DominoKit/assets/domino-kit.png "Domino Kit")

Recently, I've been thinking about building table top games in Swift. And today I decided to take another step in the direction by building a simple library called [DominoKit](https://github.com/jarrodparkes/DominoKit)!

```swift
import DominoKit

let sixEight = Domino(suitOne: .six, suitTwo: .eight)
print(sixEight) // "[06|08]"
print(sixEight.suitOne) // "06"
print(sixEight.suitTwo) // "08"
print(sixEight.isDouble) // false
print(sixEight.isSingle) // true
print(sixEight.rank) // 14
```

As you can see in the code example above, the primary purpose of the library is to define a `Domino` type that can be used in other applications. Because it is only available through the [SwiftPM](https://swift.org/package-manager/) that really only means command line applications right now, but eventually I want to expand it to anything Cocoa. Anyways, I hope some people try it out. I'm going to give it a test run in a few days by building a command line version of [Chicken Foot](https://en.wikipedia.org/wiki/Chicken_foot_(game)).
