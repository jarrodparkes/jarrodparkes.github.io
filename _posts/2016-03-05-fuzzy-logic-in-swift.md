---
layout: post
title:  Fuzzy Logic in Swift
date:   2016-03-05 
tags:
---

I've determined the reason that I cannot play video games at length anymore. Every time I play a game, it leads me into a new development project and I get sidetracked from actually playing the game. Most recently, I was tinkering around with [Viva Piñata](https://en.wikipedia.org/wiki/Viva_Piñata), an old favorite of mine, and I thought to myself "maybe I can recreate the logic used by the piñata animals". Of course, I don't really know how the developers created everything, but I assumed maybe a fuzzy logic system is being used to determine animal behavior. So, I built my own fuzzy login system in Swift. You can contribute to the project on [Github](https://github.com/jarrodparkes/fuzzy-swift).

The system is built using a few primitives:

- Point
- Line
- FuzzySet
- FuzzyVariable

## Point

A struct representing a point in 2D-space.

## Line

A struct representing a line segment. It is composed of a slope, minimum x-value, maximum x-value, and the line's functional representation. The functional representation is a closure that can used to produce a y-value in the format of `y = f(x)`.

## FuzzySet

A struct that contains a collection of Line objects (line segments) which form a shape that can be represented on a 2D graph/chart. The main purpose of this struct is to generate membership values (percentages) based on a value related to a FuzzyVariable.

## FuzzyVariable

A struct that contains a collection of FuzzySet objects. Given a value, one can calculate the degree of membership for all associated FuzzySet objects.

## References

- Game Programming Gems 2
- ["Fuzzy Logic for Games" by Purvag Patal](http://purvag.com/blog/?p=284)
- [Real-Time Game Design of Pac-Man Using Fuzzy Logic](http://ccis2k.org/iajit/PDF/vol.3,no.4/7-Adnan.pdf)
- [jFuzzyLogic: Open Source Fuzzy Logic Library (Java)](http://jfuzzylogic.sourceforge.net/html/manual.html)
- [Artificial Intelligence for Games, pg. 378](https://books.google.com/books?id=1OJ8EhvuPXAC&pg=PA378&lpg=PA378&dq=defuzzification+games&source=bl&ots=iUVJtjUZDv&sig=qSbIlwFw1BcorzebnO2y3aCGtTQ&hl=en&sa=X&ved=0ahUKEwiV262Nr8jKAhWERyYKHeRHCagQ6AEIJjAC#v=onepage&q=defuzzification games&f=false)
- [Emergence in Games, pg. 128](https://books.google.com/books?id=macLAAAAQBAJ&pg=PA128&lpg=PA128&dq=defuzzification+games&source=bl&ots=PEzdCFrW1c&sig=ML-lF1qmv1rzeO3vb8IAjicaZDc&hl=en&sa=X&ved=0ahUKEwiV262Nr8jKAhWERyYKHeRHCagQ6AEIPTAI#v=onepage&q=defuzzification games&f=false)
