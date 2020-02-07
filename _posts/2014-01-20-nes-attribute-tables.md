---
layout: post
title: NES Attribute Tables
date: 2014-01-20 
tags: nes
---

![nes-attribute-tables]({{ site.url }}/images/nes-attribute-tables.png "NES Attribute Tables")

> Painted Tile Image: Taken and Produced by [Chelsea Rominski](http://mygoodmorning.com/) for her [DIY Tile Painting Project](http://mygoodmorning.com/2013/05/16/painting-tiles-coffee-table-revamp/).

Following my last post on [NES Nametables](https://www.jarrodparkes.com/nes-nametables/), I will be introducing the attribute table. An attribute table is a mechanism for applying color to NES backgrounds. Unlike a nametable, the attribute tables consists of values that correspond to 32x32 pixel regions. Each 32x32 pixel region overlaps with 16 background tiles from a nametable (except for the edge regions). The image below shows how a NES background (nametable) may be subdivided by the attribute table.

![NES Attribute Table Split]({{ site.url }}/images/nes-attribute-split.png "NES Attribute Table Split")

## How does an attribute table apply color?

Based on the image above, there are a total of 64 attribute table regions. For each region, a full byte is used--making each attribute table 64 bytes wide. Each byte is split into 2-bit values that determine the color palettes to use on the underlying tile areas. And each 2-bit pair will determine the color for a group of 4 tiles. As you may have guessed, the 2-bit values can correspond to any of the 4 background sub-palettes supported by the NES PPU. Some example sub-palettes are shown below, as well as a tile region modified by an attribute table.

![NES Attribute Example]({{ site.url }}/images/nes-attribute-example.png "NES Attribute Example")

If you are paying very close attention, you may have noticed that each sub-palette shares the same first color. The first color in each sub-palette is what is know as the backdrop color. The backdrop color becomes more important when sprites are added to the mix, but that is for another day.

So there you have it, a colored NES background. The nametable specifies the tiles to use, and the attribute table specifies the colors to use for the tiles. All of this data is held in RAM on the NES PPU. Since these values can be overridden (since they are in RAM), the real fun happens when you alter the values during runtime!

## How can you get started with NES graphics?

I have great news. If you would like to start playing around with NES graphics right now, try this excellent resource from [http://fsp.fm/wrk/playpower/](http://fsp.fm/wrk/playpower/).

Happy hacking.
