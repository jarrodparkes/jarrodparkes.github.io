---
layout: post
title: NES Nametables
date: 2013-12-20 
tags: nes
---

![nes-nametables](https://s3.us-east-2.amazonaws.com/jarrodparkes.com/nes-nametables.png "NES Nametables")

> 8-Bit Seattle Cityscape: Created by [W. Miles Donovan](http://the-daily-robot.tumblr.com/post/51098163500/metropixelated-these-are-the-first-3-entries-in).
NES Color Palette from [NES Hacker - The Mighty Guru Site](http://www.thealmightyguru.com/Games/Hacking/Wiki/index.php?title=NES_Palette).
Pixel Graphics from [1 More Castle Blog Post](http://1morecastle.com/2012/08/an-nes-homebrewers-rant-wasted-weekends-are-a-part-of-the-process/) (Dragon Warrior).

In the mid-80's, the NES helped usher a new era of popular video games. Its success can be attributed to many things, but improved graphics is definitely near the top. Unlike many console games of the 70's (*cough* games on the Atari *cough*) that lacked strong visual appeal, the NES games supported better colors and richer environments. The time for completely black backgrounds and an overabundance of "space" games had ended.

So, from a programmer's perspective, what had changed to improve the graphics of the day? The simple answer is the hardware (buffered graphics), but we will take a more focused look at one component--the NES nametable.

## What is a Nametable?

A nametable is a background layer with unique qualities. First, nametables are split into 30 rows and 32 columns of 8x8 pixel tiles. This makes for a total resolution of 30x32 tiles or 256x240 pixels. Each tile is represented by one byte holding a value from 0-255. This means it takes 960 bytes to represent all the tiles. The value at each tile represents a lookup value into a pattern table. Because pattern tables are a separate subject, they may be thought of as sprite sheets. The example below shows a subset of a sample pattern table and nametable.

![Nametables-ex-1](https://s3.us-east-2.amazonaws.com/jarrodparkes.com/nametable-ex-1.png "Nametables-ex-1")

![Nametables-ex-2](https://s3.us-east-2.amazonaws.com/jarrodparkes.com/nametable-ex-2.png "Nametables-ex-2")

Now, the image above has a caveat...I have intentionally left out the color. Why? Because bundled with each nametable is an attribute table. An attribute table allows 2x2 groups of tiles to be colored by one of four color palettes, and I will talk about them in an upcoming blog post. When you combine everything: a pattern table, a nametable, and an attribute table, you can produce a full screen of NES 8-bit goodness!

![Nametables-ex-3](https://s3.us-east-2.amazonaws.com/jarrodparkes.com/nametable-ex-3.png "Nametables-ex-3")

This is only the tip of the iceberg for NES nametables. Along with the above complexities, the NES allows multiple nametables to be in memory at one time. Additionally, the hardware supports the ability to scroll between nametables. Because of the scrolling feature, it makes since why there was a rise of side-scrolling adventures on the NES. Also, I have not discussed the global color palette. It is shown below for reference (a more lengthy [discussion](http://www.thealmightyguru.com/Games/Hacking/Wiki/index.php?title=NES_Palette) about the palette). For now, this should be enough to chew on.

![nametable-color-palette](https://s3.us-east-2.amazonaws.com/jarrodparkes.com/nametable-color-palette.png "nametable-color-palette")