---
layout: post
title: Making Pokemon Clone in Swift with SpriteKit
date: 2015-04-02 22:53:12-0600
tags: ios
---

It is time I embarked on a new side project. Since I am doing iOS development in Swift at work, the natural choice is to learn something that is iOS-related and uses Swift. My choice—SpriteKit.

![sprite-kit-banner]({{ site.url }}/images/sprite-kit-banner.png "sprite-kit-banner")

SpriteKit is an Apple framework tailored for building 2D games, so why not start by building a classic 2D clone? My choice, of course, is Pokemon. But, since I am going to keep this simple, we might want to call it **"Ash Fights a Charmander"**. Anyways, let's get down to the basics: how do you build a game in SpriteKit? Here is the material I used to get started...

- [Apple: About Sprite Kit](https://developer.apple.com/library/ios/documentation/GraphicsAnimation/Conceptual/SpriteKit_PG/Introduction/Introduction.html)
- [Ray Wanderlich: Sprite Kit Tutorial for Beginners](http://www.raywenderlich.com/42699/spritekit-tutorial-for-beginners)
- [Ray Wanderlich: How To Create a Breakout Game with Sprite Kit and Swift](http://www.raywenderlich.com/84341/create-breakout-game-sprite-kit-swift)

I'll save a lengthy discussion on SpriteKit for a later day and just focus on the classes you need to know. First, all SpriteKit games take place within a **SKView**. A **SKView **is a subclass of UIKit's **UIView** and it is used to present a **SKScene**. For Pokemon (Red and Blue Versions), there are two main scenes: the world scene and the battle scene.

![World Scene]({{ site.url }}/images/pokemon-world-scene.jpg "World Scene")

![Battle Scene]({{ site.url }}/images/pokemon-battle-scene.jpg "Battle Scene")

A scene, and most of the items within it, are instances of **SKNode** or its various subclasses. The subclasses include [SKSpriteNode](https://developer.apple.com/library/ios/documentation/SpriteKit/Reference/SKSpriteNode_Ref/index.html#//apple_ref/occ/cl/SKSpriteNode) (for sprites), [SKLightNode](https://developer.apple.com/library/ios/documentation/SpriteKit/Reference/SKLightNode_Ref/index.html#//apple_ref/occ/cl/SKLightNode) (for lights), etc. If you have used Unity before, then these nodes are somewhat analogous with GameObjects. Like GameObjects, they can be nested within each another or organized on separate layers. So, from the world scene above, we might say that Ash and the villagers are nodes in a "character layer".

And... that is basically all I needed to get started! I'll write a more extensive guide once I have something tangible, but here is my first night's work: a simple screen with movement and collision detection (you've got to start somewhere).

![sprite-kit-screen-0]({{ site.url }}/images/sprite-kit-screen-0.png "sprite-kit-screen-0")

![sprite-kit-screen-1]({{ site.url }}/images/sprite-kit-screen-1.png "sprite-kit-screen-1")