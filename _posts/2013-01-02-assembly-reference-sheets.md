---
layout: post
title: Assembly Reference Sheets
date: 2013-01-02 04:51:53
tags: gamedev
---

![nes-asm-back]({{ site.url }}/images/nes-asm-back.png "NES Assembly Background")

For relatively new assembly programmers, such as myself, remembering each command/mnemonic is difficult and often not necessary. A wise man named Albert Einstein once said, "Never memorize what you can look up in books." So using his approach, I thought it would be a good idea to consolidate the instruction sets of each assembly language I have been exploring into an easy-to-use assembly reference sheet. In fact, I took it a step further and made the assembly reference sheets into high resolution backgrounds.

> "Never memorize what you can look up in books." - Albert Einstein

Since I learn well with visual cues, each of the assembly reference sheets comes with stylized version of the console and typography to match. In all, I completed a background for the NES, Sega Genesis, Gameboy, and Dreamcast VMU or "Virtual Memory Unit". Here is the [NES background](https://www.jarrodparkes.com/wp-content/uploads/nes-asm-back.png). The rest can be viewed below.

## Assembly Reference Sheets

![genesis-asm-back]({{ site.url }}/images/genesis-asm-back.png "Genesis Assembly Background")

Of all the sheets, the Genesis was probably the most tricky. I had to really play around with the real estate of the image on this one. There are definitely more commands for the Motorola 68k; however, there is still probably some work I could have done to reduce how many I listed. For instance, most of the commands expand to work on different data sizes like 8-bit, 16-bit, and 32-bit: I could have condensed the commands to the least common denominator and left the expanded versions of the commands off of the sheet.

![gameboy-asm-back]({{ site.url }}/images/gameboy-asm-back.png "Gameboy Assembly Background")

Here is the sheet for the Gameboy. Not much to say here except it was a little more difficult to hunt down documentation online about the command set.

![dreamcast-vmu-asm-back]({{ site.url }}/images/dreamcast-vmu-asm-back.png "Dreamcast VMU Assembly Background")

This last assembly reference sheet is really an oddity because it involves a more modern console. My guess is most programmers for the Dreamcast would use something like C or C++ to code games unless they were digging down and optimizing code; however, the VMU, is a separate case. The documentation for this was really hard to find, but here is this little gem of a codebase [http://mc.pp.se/dc/](http://mc.pp.se/dc/).

Just a side note, each of the assembly reference sheets do assume some knowledge of how the assembly commands function. Again, the point of these sheets is to have a quick reference to what a command does at a high level. Understanding how you can string these commands together to create good assembly code is truly a work of art, and it takes practice.

Feel free to share these and use them in your own development.
