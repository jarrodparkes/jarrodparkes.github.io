---
layout: post
title: RB3 NES Homebrew Game
date: 2012-12-27 
tags: nes
---

![rb3-cover]({{ site.url }}/images/rb3-cover.png "Red Block Blue Block")

I am finally ready to announce my first NES homebrew, Red Block Blue Block (RB3). RB3 is a simple game that pits a red block against an army of blue blocks. The style of the game is based on simple arcade classics like Snake and Space Invaders. RB3 is still a work in progress, but it is currently on stable release RB3 v1.1.1. I intend on using this project as an ongoing testbed for my NES development.

In RB3, you must take control of a lone red block and travel through multiple levels of a block world. In each level, you can collect powerful items to aid in your destruction of all of the blue blocks.

My purpose for creating RB3 was to test all of the subsystems of the NES in a simple game. I wanted to become familiar with how to draw graphics, generate sound, and process controller input on NES in pure 6502 assembly. So, as I take on bigger projects, I can always come back to RB3 for inspiration and ideas.

## Game Features

1. basic player controls
2. ability to fade in/out of graphics
3. sprite movement
4. boundary detection
5. simple collision
6. memory bank switching to add additional graphics

Below is the most recent RB3 gameplay footage.

<div class="video-wrapper">
    <iframe width="640" height="360" src="https://www.youtube.com/embed/n5TgZdyWYL8" frameborder="0" allowfullscreen></iframe>
</div>