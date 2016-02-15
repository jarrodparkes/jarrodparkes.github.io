---
layout: post
title: Zomblings AI Prototype
date: 2009-11-01 08:04:17-0600
tags: unity3d
---

![zomblings-cover]({{ site.url }}/images/zomblings-cover.png "Zomblings")

Zomblings was my first attempt at developing basic computer AI in Unity3D. The capsule-shaped enemies are called “zomblings”, and yes they are zombies. For their pathfinding, they do not move within a grid system like more classical approaches. Instead, each zombling tracks through an array of waypoints and nodes that are placed around the arena. This design was more consistent with the pathfinding in more modern 3D games.

Because I wanted something more than a simple shot-and-kill design, I decided to let the zomblings be baited around the map. This way, I could use the zomblings as cannon fodder or to help accomplish tasks in the environment. In fact, by incorporating the baiting techniques, players are required to accomplish certain mission objectives or face an untimely death.

For the demo seen below, the objective was to destroy the watch tower at the end of the map. In the watch tower, a super zombling capable of firing a machine gun sprays bullets on the player. So, by baiting the ground zomblings, and carefully navigating around obstacles, the player is able to lead a zombling through the fire and to the explosive barrel near the watch tower. If done correctly, the explosive barrel ignites and destroys the watch tower and super zombling.

<div class="video-wrapper">
	<iframe width="640" height="360" src="https://www.youtube.com/embed/SYf1E3mg3KU" frameborder="0" allowfullscreen></iframe>
</div>
