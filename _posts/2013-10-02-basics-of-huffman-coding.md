---
layout: post
title: Basics of Huffman Coding
date: 2013-10-02 10:50:10-0600
tags: nes
---

![huffman-basics-cover]({{ site.url }}/images/huffman-basics-cover.png "Huffman Basics")

> Battletoads Huffman Example Images: Provided by [Brad Smith](http://rainwarrior.ca/).
YouTube Huffman Compression Video: Provided on [Travelschlepp's Channel](http://www.youtube.com/user/travelschlepp/about).

I originally started this article almost a month ago, but I am finally getting around to finishing it. Today I am going to tackle the topic of Huffman (en)coding. Huffman encoding/decoding are compression algorithms designed to compress and decompress data. I first started tinkering with Huffman coding when I ran across this [post](http://forums.nesdev.com/viewtopic.php?t=8609) on the NesDev forum by Brad Smith aka "RainWarrior". In the post, Brad investigates the Huffman code he noticed while disassembling the NES classic Battletoads.

## How does Huffman coding work?

I am going to try to avoid the extremely technical terms. I apologize if this is a "watered down" synopsis, but if it is hard to understand, make it simple!

Part 1: Compressing the Data

- Take a data set
- Split the data set into symbols
- Determine the frequency of each symbol (how often it occurs)
- Construct a binary tree by combining the symbols and their frequencies into nodes
- Compress the original data set by traversing the binary tree and encoding data based on the path taken to reach each symbol's node

Part 2: Decompressing the Data

- Take a data set that has been Huffman encoded
- Take a binary tree that corresponds to the Huffman encoded data
- Decompress the data by traversing the binary tree along encoded paths until reaching leaf nodes

**What happened to keeping it simple?**

Do not worry! When I first started studying Huffman coding, it took me a whole weekend to understand the process. So, I have created some visual examples to drive home the concept.

![huffman-map]({{ site.url }}/images/huffman-map.png "huffman-map")

Above, is a simple image of some random tiles arranged into a map. For the sake of example, let us assume that **each tile takes 1 byte to represent**. Since the map consists of a total of one-hundred tiles, then that means the map takes 100 bytes to represent (100 tiles x 1 byte per tile). So our goal for this Huffman compression is to reduce the size of the mapper to less than 100 bytes!

To begin, we must analyze our basic symbols. In this case, our symbols are the tiles themselves. We have a total of 5 symbols: wood, stone, grass, dirt, and water. Then, we must calculate their frequencies in the map. This has been completed in the image below.

![huffman-freq]({{ site.url }}/images/huffman-freq.png "huffman-freq")

Now, we must construct our Huffman tree and encode each tile. For this step, here is wonderful [YouTube video](http://youtu.be/0PahtaFK640) that describes the process using letters instead of map tiles. Before I found this video, I was in the dark... so hopefully it will be equally helpful for you. Continuing with this example, I have included the steps to create a single node in the Huffman tree. You continue doing the process until all symbols have been added to the tree.

![huffman-creating-nodes]({{ site.url }}/images/huffman-creating-nodes.png "huffman-creating-nodes")

![huffman-tree]({{ site.url }}/images/huffman-tree.png "huffman-tree")

At this point, the bulk of the algorithm is over. Our last step is to encode a symbol (tile) by traversing the Huffman tree. To encode the entire map, we would need to encode each tile; however, since this process becomes trivial, I have only shown how to encode one wood tile. Also, the decompression is exactly the same, but in the reverse order.

![huffman-traversal]({{ site.url }}/images/huffman-traversal.png "huffman-traversal")

So, in the above example we have saved 5 bits for the single wood tile. By doing some quick math, we can see that for wood tiles we will save a total of 45 bits (9 wood tiles x 5 bits saved per wood tile) for the entire map. If we run the algorithm for the full map, we will save a total of 574 bits or 71.75 bytes (the new map will be only 28.25 bytes). Thus, our compression rate is about 71.75%, not too shabby! Or to sound more impressive, you could say the original map is more than 3 times the size of our compressed map!

You will find that the effectiveness of Huffman coding (like all compression algorithms) depends on your data set. There are many articles which describe the optimal use-cases for such an algorithm, but I will leave that topic for another day. In closing, I will leave you with this following image provided by Brad Smith... the Huffman tree used by Battletoads. Awesome!

![huffman-battletoads]({{ site.url }}/images/huffman-battletoads.png "huffman-battletoads")