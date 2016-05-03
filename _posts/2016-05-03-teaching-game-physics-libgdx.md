---
layout: post
title:  Teaching Game Physics with Box2d and libGDX
date:   2016-05-03 10:00:30-0600
tags:	libgdx
---

Learning and teaching game physics, has been my focus the past month. At first, I was very apprehensive to take on a completely new topic -- I never took physics in high school or college -- but, I believe that my inexperience has better prepared me to teach newcomers. The fruit of my month-long labor is a sandbox of physics demos built with Box2d and libGDX.

![group-select-screen]({{ site.url }}/images/group-select-screen.png "Demo Group Selection Screen")

Currently, the sandbox has 25 demos that fall into 1 of 5 different categories: basic, force, collision, joint, and structure, and is completely extensible if future contributors want to add demos. The code in each demo reads like a blog post and shows you how to create physics objects and constraints that control the physics simulation you see on screen. You can play with a [web version of the sandbox](http://udacity.github.io/libgdx-physics-sandbox/). The full source code will ship with a physics course at Udacity later this year.

![physics-sandbox-gameplay]({{ site.url }}/images/physics-sandbox-gameplay.png "Physics Sandbox Gameplay")