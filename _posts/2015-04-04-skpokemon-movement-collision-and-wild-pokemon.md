---
layout: post
title: SKPokemon Improvements
date: 2015-04-04 20:56:13-0600
tags: ios
---

I've come up with a name for this project... SKPokemon (using the SpriteKit naming convention).  Today and yesterday, I tinkered with texture-based collisions and transitioning between **SKScene** objects. Less notably, I quickly modified the movement code so that I can walk around the map in all four cardinal directions. Here's the wrap:

## Texture-Based Collisions

SpriteKit uses instances of the **SKPhysicsBody** class for incorporating physics and collision detection. Like other games engines, you can create primitive physics bodies like squares and circles, or use something more complex like texture-based physics bodies—this is what I am currently using for the simple background/world. With the debugging properties of SKView enabled, you can see the outline of the scene's physics bodies.

![skpokemon-1]({{ site.url }}/images/skpokemon-1.png "skpokemon-1")

The blue lines are the bounds of the physics bodies. Although the full background consists of grass and trees, the texture-based collision isolates which parts (i.e. tall grass) should detect collisions.

In code, it looks like this...

```swift
background.physicsBody = SKPhysicsBody(
  texture: SKTexture(imageNamed: "pokemon-world-1-collision"),
  alphaThreshold: 0.0,
  size: CGSize(width: 720, height: 720)
)
```

While this is nice, it is not a silver bullet. Creating physics bodies for the entire region of Kanto will surely not be done with textures. Instead, a more sound solution would be to procedurally generate the world (and its physics bodies) from data files. Since this is a heavier task and I am rushing to get to a minimum viable game, my plan is to work on that system later. Instead, my upcoming work will focus on the battle system... which leads me to my next point, transitioning the **SKView** to the battle scene!

## SKScene Transitions

For now, the only scene transitions in SKPokemon are between the world and battle scenes. Because I was already detecting collisions between the player and the grassy areas, I was halfway to switching scenes. The second half is an easy snippet of code, but like much of this project it is extremely brute-force and messy—I'll be fixing that piece by piece. If I have learned anything from building little game prototypes, it is to start EXTREMELY small so that you have something you can play. Then keep building... and keep building... and keep building.

As always, mandatory screenshots! If you are thinking the graphics look ripped, then you are right. Hackers be hackin'!

![skpokemon-20150404-2]({{ site.url }}/images/skpokemon-2.png "skpokemon-20150404-2")