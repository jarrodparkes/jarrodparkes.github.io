---
layout: post
title: NES Assembly Curriculum
date: 2013-04-21 
tags: nes
---

![teaching-assembly-cover](https://s3.us-east-2.amazonaws.com/jarrodparkes.com/teaching-assembly-cover.png "Teaching Assembly Book Cover")

When I refer to "NES assembly" in this post it can be swapped interchangeably with 6502 assembly.

For my technical writing assignment this semester, I wrote [a paper](https://s3.us-east-2.amazonaws.com/jarrodparkes.com/nes-assembly-curriculum.pdf) describing how the UAH Computer Science Department SHOULD TEACH assembly languages. My proposal was the course should be taught using NES Assembly or the 6502 processor family as the focal point. Currently, the department teaches assembly language programming using the x86 family of processors. Although the x86 processor family is feature-rich and modern, most students will never program in assembly for them. In most applications, the assembly code is automatically generated by compilers and not written by humans. So, since the class is more about teaching core concepts of programming and computer architecture, I proposed a curriculum using NES assembly.

Although the NES is an outdated console from the 1980s, the concepts it can teach still remain--I make this fact well known throughout the paper. To open, I stress that learning NES assembly language is really about learning how a computer functions. After the introduction, the paper is divided into six action-packed chapters.

-  The Class Project
- Number Systems and Data Representation
- The 6502 Instruction Set
- Assemblers and Related Tools
- NES Hardware Basics
- The Game Loop

In each chapter, I explore topics while giving students ways to use the new material in their class project. Ultimately, I think the class project is the most valuable part of the curriculum. The class project breaks students into small teams to create their own games, and it really encourages the creative thought  needed for all facets of game design. To give you an idea of the content, here is a snipped from Chapter 2: "Number Systems and Data Representation". All the figures were created in Adobe Photoshop (I was pretty pleased with the results).

## Excerpt from Chapter 2
Like the traffic lights in Figure 2.1 [not shown], electrical memory components in a computer flash, or change from high to low, in the presence of binary ones and zeros. For automobile drivers, a flashing traffic light may represent whether to stop or yield at an intersection; however, in a modern computer, flashing memory components may represent numbers or processes. When automobile drivers, computers, or programmers derive meaning from symbols, they are **interpreting** or **representing** data. Below, Figure 2.2 demonstrates how the NES graphics processor interprets color information from binary numbers.

![nes-assembly-attribute-example](https://s3.us-east-2.amazonaws.com/jarrodparkes.com/nes-assembly-attribute-example.png "NES Assembly Attribute Example")

## Closing Thoughts

The paper is a small effort of mine to start teaching programming. Over the years at UAH, I have grown disgruntled by how the CS Department teaches programming concepts. Not only is most of the coursework out-dated, but the professors seem genuinely uninspired about teaching programming. In my opinion, the way programming should be taught is similar to how I learned NES assembly through the homebrew community at [NintendoAge](http://nintendoage.com/)–with awesome (short) tutorials and straight-forward advice. I hope the paper (or pieces of it) will make their way to NES homebrew community; however, there are many out there with way more knowledge on the subject than me.
