---
layout: post
title: Monkey Arena FPS
date: 2009-04-01 
tags: unity3d
---

![monkey-arena-cover]({{ site.url }}/images/monkey-arena-cover.png "Monkey Arena")

Monkey Arena is a multiplayer FPS game I created in the Unity3D game engine. This was the first installment of a series of monkey-theme games I worked on with my twin brother. Monkey Arena was largely influenced by Halo, Call of Duty, Donkey Kong 64, and Team Fortress 2 for its cartoon/cell-shaded graphics.

The first prototypes for the game focused on creating the gun logic. I developed the controls and physics for five unique weapons.

1. watermelon rocket launcher
2. strawberry pistol
3. grape assault rifle
4. pineapple sniper rifle
5. blueberry shotgun

Each weapon was based on a real gun, but their themes were based on fruits. For weapons like the rocket launcher and sniper rifle, I included "down-the-scope" zooming features and physics-based blast radiuses for explosions. Other gameplay elements which I scripted were bullet release timing, reload times, and bullet damage falloffs based on velocity. So while the game contained unrealistic characters, the gunplay focused on precision as seen in more realistic FPS games.

For each of the gameplay elements, I also created a custom user interface that allowed game testers to edit values on the fly. I accomplished this by overriding Unity's inspector GUI system. The final element I contributed to was the radar seen in the top-left hand corner of the Monkey Arena gameplay video. This simple radar-blip system tracked the positions of nearby enemies. All of the GUI was created by my twin brother James.

<div class="video-wrapper">
    <iframe width="640" height="360" src="https://www.youtube.com/embed/DvEvQvvq4mQ" frameborder="0" allowfullscreen></iframe>
</div>