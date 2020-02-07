---
layout: post
title:  Layout Variance and Traits
date:   2016-09-30 
tags:	ios
---

I was updating an iOS app at work, and I stumbled upon Xcode's feature for layout variance based on traits. What are traits, you ask? They are the width, height, and gamut of Apple devices. Width and height are self explanitory, and gamut is related to the graphics hardware (I think). Anyways, Xcode storyboards give you the ability to modify UI element values based on traits (or trait families). For example, if I want the elements in a view to be positioned in a certain way for landscape, but in a different way for portrait, then traits give me an easy way to do it.

I'm going to walk through a simple example using a toy app I built called AnimalFriends. Here, are screenshots of the app in landscape and portrait mode.

![animal-friends-screens]({{ site.url }}/images/animal-friends-screens.png "AnimalFriends App in Portrait and Landscape Modes")

While the UI elements for each orientation are the same, the properties for these elements differ based on traits. Specifically, I'm utilizing the height trait to determine the orientation of stack views which position everything on screen.

![animal-friends-traits]({{ site.url }}/images/animal-friends-traits.png "Modifying Properties Based on Traits for AnimalFriends")

In the above screenshot, you can see where I am attempting to add a new variant to a stack view based on the traits of the currently simulated device (iPhone 6s Plus) in storyboard. The dialog in the image appears by clicking on the plus sign icon next to the Axis property, but the same would be true if I clicked on the plus sign next to any property that has the ability to change based on traits. As evident in the dialog, the iPhone 6s Plus has a width that is considered Regular, a height of Compact, and a gamut of Any. If I were to click "Add Variation", then I would be granted the ability to change the Axis for this particular variation of traits.

Ignoring the dialog in the image, you can see that I've already added variations for what is displayed as "hC" ("height compact") under both the Axis and Distribution properties. Hence, whenever this stack view is displayed on a device that has a height that is consider compact, then the Axis will be set to Horizontal instead of Vertical. Pretty neat, huh?

Anyways, I'm just scratching the surface with this feature, and I hope to share more soon!

Check out [the repository for Animal Friends](https://github.com/jarrodparkes/AnimalFriends). The images used in the app are free for commerical use, and they can be found on [Creative Tail](https://www.creativetail.com/40-free-flat-animal-icons/).
