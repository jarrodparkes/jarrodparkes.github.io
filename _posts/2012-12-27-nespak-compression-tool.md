---
layout: post
title: NESPAK Compression Tool
date: 2012-12-27 
tags: nes
---

![nespak-cover]({{ site.url }}/images/nespak-cover.png "NESPAK Compression Tool")

NESPAK is a simple command-line tool I created to compress data for my NES games. NESPAK supports RLE, LZ-78, and Huffman compression types.

As I started doing more sophisticated NES programs, I quickly noticed that size was starting to become a big constriction. So, I took time away from game development to learn about general compression algorithms. Once I had a firm enough grasp on some compression types, I created NESPAK to take help compress data that was being used in my NES development. I started with run length encoding (RLE) because it was the most simple and it was very applicable to the title screens I had created in my games. Since title screens contain many repeat tiles, RLE is able to compress strings of duplicate tiles into "runs" with an associated length values. This greatly decreased the memory footprint of my title screens by about 60% in standard cases.

Next, I began looking into ways to compress text data for games with complex dialogue systems. I found this [awesome thread on Huffman compression](http://forums.nesdev.com/viewtopic.php?t=8609) describing how it is used throughout the NES game Battletoads. This lead me to add Huffman compression to NESPAK. I am still in the process of incorporating Huffman compression into one of my games, but I am yet to implement the decryption portion that must take place on the NES.