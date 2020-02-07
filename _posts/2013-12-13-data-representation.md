---
layout: post
title: Data Representation
date: 2013-12-13 
tags: dev
---

![data-representation-cover]({{ site.url }}/images/data-representation-cover.png "Data Representation")

> Realistic Lightbulb Drawing: Provided by [Marcello Barenghi](http://www.marcellobarenghi.com/). ASCII Table from [http://www.asciitable.com/](http://www.asciitable.com/).

Yes! I am finally back after a long, trying semester of college. To reorient myself with posting on this blog, I feel it is appropriate to recharge with the introductory programming concept of **data representation**. From my time serving as a Computer Science tutor, data representation was a problem I saw students repeatedly struggle with—how to bridge the gap between data and the structures they represent. To discuss this topic, I am going to pull a page out of the paper my brother James and I wrote for our EH 301 (Technical Writing) course at UAH. This first excerpt comes from Chapter 2 titled "Number Systems and Data Representation". It is about the binary number system, which is used throughout the rest of this post.

## **Binary Introduction**

Computers use the **base-2 number** system—more commonly referred to as **binary**. The digit "2" in the word "base-2" is related to the two values used in the binary number system: "0" and "1". By combining 0's and 1's, we can create binary numbers—each digit in a binary number is known as a bit. For computers, the bits zero and one have the special meaning of being either "on" or "off", "true" or "false", "high" or "low". These special meanings refer to whether or not a component in a computer is holding a specific electrical voltage. To avoid confusion, see the simple visual example (below) in Figure 2.1.

![data-representation]({{ site.url }}/images/data-representation.png "data-representation")

## **Binary to Symbols, Symbols to Meaning**

Like the traffic light in Figure 2.1 (above), electrical memory components in a computer change based on the electric voltage. For automobile drivers, a flashing traffic light may represent whether to stop or yield at an intersection; however, in a computer, the 0's and 1's in memory components may represent numbers, images, or anything your heart desires (well mostly anything). When automobile drivers, computers, or programmers derive meaning from symbols like the 0's and 1's, they are interpreting or representing data.

## **Common Data Representations**

So how can we string 0's and 1's together to represent data? Arguably, we could do this anyway we want, but there are some common, practical ways that everyone should know. You may hear these referred to as "encodings", but again that is just another fancy word for data representation. As an example, I will outline two common encodings: ASCII and unsigned integers. From system to system, these encodings may differ slightly, but they follow the same general standards mentioned below.

ASCII Encoding (8-Bit): Before looking at ASCII, you will need to know some quick math. Since a bit can be either 0 or 1, we might say there are 2 possibilities for each binary digit. And since ASCII characters are composed of 8-bits, that means there are 8 bits with 2 possibilities each. In total, that means there are 2^8 or 256 possible combinations of 8-bits

Okay, so now that we know there are 256 ASCII symbols, what are they? Well, here is a great chart showing the first 128 symbols from [http://www.asciitable.com/](http://www.asciitable.com/) (follow the link to see all the symbols). Remember: ASCII is one specific data representation... you are using 8-bits to represent 256 unique characters.

![ascii-table]({{ site.url }}/images/ascii-table.gif "ascii-table")

Unsigned Integer (16-Bit): Now, we will look at a slightly more complex example, unsigned integers. What are they? Unsigned integers are positive numerical values without a fractional or decimal component. You may have heard these referred to as whole numbers, but because we are talking about unsigned integers, we are only referring to positive whole numbers. For this example, we are representing unsigned integers as 16-bit values. Similar to the math from the previous example, we have 2^16 or 65,536 possible combinations of 16-bits. Beginning with the smallest value 0, we have the ability to encode the unsigned integers from 0-65,535. Here are some sample unsigned integers and their binary representations in 16-bits. Maybe in a later post, I will explain how to go from the binary representations to unsigned integers using positional notation.

- 0 --&gt; 0000 0000 0000 0000
- 1,986 --&gt; 0000 0111 1100 0010
- 6,593 --&gt; 0001 1001 1100 0001
- 2,313 --&gt; 0000 1001 0000 1001
- 65,535 --&gt; 1111 1111 1111 1111