---
layout: post
title: SegaCD Transfer Cable to Run Code
date: 2012-10-22 02:20:52-0600
tags: genesis
---

![segacd-transfer-cover]({{ site.url }}/images/segacd-transfer-cover.png "SegaCD Transfer Cable")

I started this project a couple weeks ago, but I am finally getting around to writing about it. When I first started Google-searching homebrew development for the Sega Genesis, I stumbled upon an article called "The SegaCD Transfer Cable". The article discussed how to use a connection from a PC parallel port to the 2nd player port on the Genesis in order to run homebrew code. The biggest snag in the article was creating the custom cord that took a 25-pin parallel cable and converted it to a 9-pin controller connection. With the help of some friends, I was able to make the SegaCD transfer cable myself. Also, the cable requires a SegaCD to run the bootstrap code.

The instructions to build the SegaCD transfer cable can be found at [http://www.retrodev.com/transfer.html](http://www.retrodev.com/transfer.html" target="_blank).

Overall, the process was not too difficult, even if you have no experience with wires or opening peripherals. I had to sacrifice a perfectly good Sega Genesis controller which is my only regret. But, maybe one day I can convert the scarp parts into a wireless controller.

Anyways, after snipping both the controller wire and a standard 25-pin parallel cord in half, I was able to expose all the wires inside. Since I could not easily determine which wires went to which pin, I had to create a simple color chart. Using my digital multimeter, I measured voltage readings to map the input pins to the colored wires. If you are doing this process yourself, I would recommend finding some kind of clamp to hold the wires in place because you quickly run out of hands. After the chart was complete for both wires, all I had to do was solder the correct connections together. I got a trusted friend to help me do the soldering. Big thanks to *Chris Andrews*! Below are start-to-finish pictures of the SegaCD transfer cable.

![segacd-transfer-cable-cord-clip]({{ site.url }}/images/segacd-transfer-cable-cord-clip.png "SegaCD Transfer Cable Cord Clip")

This is after I had clipped and taped back the wires on the 25-pin cord.

![segacd-transfer-cable-pin-tests]({{ site.url }}/images/segacd-transfer-cable-pin-tests.png "SegaCD Transfer Cable Pin Tests")

Here I am reading the voltage through the pin holes and the colored wires.

![segacd-transfer-cable-pins]({{ site.url }}/images/segacd-transfer-cable-pins.png "SegaCD Transfer Cable Pins")

Here is the basic pin map for the 25-pin and 9-pin wires.

![segacd-transfer-cable-heat-shrink]({{ site.url }}/images/segacd-transfer-cable-heat-shrink.png "SegaCD Transfer Cable Heat Shrink")

This is right before wrapping the entire wire back into one full cable. The white material over the connections was heat shrunk to increase the durability of the cable.