---
layout: post
title: Blanking - A Critical Time for Code
date: 2013-08-19 12:27:59-0600
tags: nes
---

![blanking-cover]({{ site.url }}/images/blanking-cover.png "Blanking")

> Blanking Cover Image: Provided by Clif Haley. Found [here](http://clifhaley.com/2012/12/09/colored-line-drawings-in-photoshop/writers-block).
Atari TIA Timing Diagram: Provided freely on [AtariAge Forums](http://atariage.com/forums/index.php).

Every video game needs graphics (even text-based video games need a way to display text to the screen). Also, every video game needs someone to create the graphics, and something to display them. Over the years, that someone and something has drastically changed. But, for the sake of brevity, I am going to focus on only one of those changes. In this post, I will address an older graphics topic called blanking. Specifically, vertical and horizontal blanking intervals also known as VBLANK and HBLANK respectively.

**So what exactly is blanking? How is it related to graphics? How is it related to game development?**

Well, the answer can be very complicated and very simple, but it all falls on an understanding of cathode ray televisions. Before flat screen LCDs, the most common television was the cathode ray television (CRT). Anyways, CRTs use an electron beam to heat parts of a phosphor-coated screen causing small particles to glow. The first CRTs used one phosphor coating that glowed white, but future CRTs used three phosphors to glow red, green, and blue (hence RGB!). To glow/emit/draw/render an entire screen, the electron beam was required to move from left-to-right in lines starting at the top of the screen and working down to the bottom. These lines are known as "scanlines". Thus, a CRT display can be thought of in terms of scanlines and screens where many scanlines make a full screen. Below is a diagram from the [AtariAge](http://atariage.com) development community showing the scanlines which build an Atari "game screen" for Pitfall.

![atari-tia-timing]({{ site.url }}/images/atari-tia-timing.png "atari-tia-timing")

Now that we have a basic understanding of CRTs, we can make the relation. Formally, blanking refers to the time it takes for the electron beam to align itself to draw a new scanline or a new screen. For example, when the electron beam finishes rendering one screen, the beam will have stopped in bottom right-hand corner where it finished the last scanline. In order to draw the next screen, the beam must travel back to the top left-hand corner to draw the first scanline of the next screen. Also, during that time, the beam should be turned off so that it does not effect anything currently displayed. This is vertical blanking or VBLANK.

The same principle applies to single scanlines. When the electron beam finished rendering one scanline, the beam will have stopped at the rightmost part of the current scanline. To draw the next scanline, the beam must travel back to the leftmost part of the screen and slightly down for the next scanline. This is horizontal blank or HBLANK.

**So now that you know the terms VBLANK and HBLANK, how are they related to game development?**

First, you must keep in mind that to the human eye, blanking occurs so fast that you cannot visibly notice the time between scanlines and screens. In fact, blanking often occurs about 50 to 60 times a second (hence frames/screens per second). But, to a computer, this blanking time is very significant. More importantly, blanking time is the ideal moment for game code to adjust graphics for the next scanline or screen. For instance, think of the Pacman character from the classic Pacman game. When Pacman moves around the screen, his position is constantly changing. So, from screen to screen Pacman is moving which means Pacman's graphics (in this case, his sprite) also need to move or update. So, what better time to for code to update Pacman's graphics than during blanking time?

Now, it is time to think a little deeper. If a game developer DID NOT update graphics during blanking time, then bad side effects COULD occur. For example, if graphics code was changed while the electron beam was moving across the screen, then unexpected graphics could be drawn to the screen. In many cases, if this happens, partial pieces of a graphic might get drawn to the screen resulting in a visual glitch or flaw. Here is an old image I took during the development of RB3 showing a glitch caused by incorrectly updating graphics during VBLANK time.

![blanking error]({{ site.url }}/images/rb3-1-1-1-bug.png "blanking error")

Lastly, blanking time is not solely limited to graphics updates. In fact, blanking time is also used to do physics calculations, scoring, and many other features in video games. In retrospect, remember that blanking is a term that translates to free time for a programmer. And by free time, I am referring to critical programming time to run important code.