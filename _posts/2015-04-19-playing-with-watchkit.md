---
layout: post
title: Playing with WatchKit
date: 2015-04-19 
tags: watchos
---

Apple opened pre-sales for the [Apple Watch](https://www.apple.com/watch/) last week which created some exciting buzz around the Bay and especially around the office. As a result, I put my SKPokemon project temporarily on the disabled list. Yes, that is a double/triple pun—SKPokemon is simultaneously disabled like a Pokemon (suffering from the effects of Thunder Wave), disabled like Dan Uggla riding the bench at the end of the Braves 2014 season, and disabled as it takes a back seat to my WatchKit experiments.

To get started with WatchKit, I completed the follow-along app examples created by Rob Percival in his [Complete Apple Watch Developer Course](https://www.udemy.com/complete-apple-watch-developer-course) on Udemy. The first of such apps was "CurrencyConvertor" which, like it sounds, converts currency. In Rob's implementation, he uses a slider (**WKInterfaceSlider**) for adjusting a base currency value which is simultaneously converted into a target currency. Here are his two interfaces:

![rob-currency-convertor-1](https://s3.us-east-2.amazonaws.com/jarrodparkes.com/rob-currency-convertor-1.png "rob-currency-convertor-1")

You'll notice that interfaces are relatively simple, but they are simple on purpose—Apple recommends clear, concise designs for the watch and it is a teaching example. But, because I wanted to challenge myself and do a deeper exploration of WatchKit, I decided to expand on his examples. So, in my "CurrencyConvertor", I added all of the currency conversions listed by [Yahoo's finance web service](http://finance.yahoo.com/webservice/v1/symbols/allcurrencies/quote) (specifically, the USD-to-target currencies). Over 150 currencies are supported!

![my-currency-convertor-2](https://s3.us-east-2.amazonaws.com/jarrodparkes.com/my-currency-convertor-2.png "my-currency-convertor-2")

I also gave the value-changing interface a facelift. This was a particularly fun and interesting challenge because Apple does not support a watch keyboard and I wanted tighter control over modifying the base value. My new value-changing interface displays the current base value, a slider for modifying amounts by place value, and the current conversion value.

![my-currency-convertor-1](https://s3.us-east-2.amazonaws.com/jarrodparkes.com/my-currency-convertor-1.png "my-currency-convertor-1")

The buttons are a little tight, but the big pay-off is being able to granularly adjust the base value amount up to 999.99 USD. Unfortunately, if you need a conversion for something higher, then you are out of luck. Maybe I will add a way to increase this maximum in a later release. Then again, it is a learning project.

## Places of Interest

![poi-selection-screen](https://s3.us-east-2.amazonaws.com/jarrodparkes.com/poi-selection-screen.png "poi-selection-screen")

My next experiment started small, but gradually grew into an entire weekend project. It is called "PlacesOfInterest". No, not an original title, but it is to-the-point. PlacesOfInterest, or "Finding POI" on iTunes Connect, is an app that allows users to find and navigate to nearby locations of interest. This is another expansion of Rob's toy applications, but I took the navigation portion much further. On the main phone interface, users can select from 12 different location types as their preferred places of interest.

The type choices are direct reflections of the types supported by the [Google Places API](https://developers.google.com/places/). For the icons, I used a map icon set from my favorite one-stop shop for test icons... [flaticon.com](http://www.flaticon.com/).

The second view (both on the phone and the watch) allows users to see a pin of a location nearest to them that is categorized as their preferred type. Since WatchKit does not allow user's to interact with maps on the watch, I included a navigation arrow which opens directions to the location on Apple Maps—pretty slick!

![poi-open-maps](https://s3.us-east-2.amazonaws.com/jarrodparkes.com/poi-open-maps.gif "poi-open-maps")

Outside of these two views, the rest of the application is plain from a user's perspective. I did not spend much time on graphics, but instead focused on straightforward A-to-B functionality. Also, while most users will not care, the application is really well-built from an architecture standpoint. Enough so that I decided to use the application as an excuse to renew my Apple Developer License and post it to iTunes Connect for TestFlight beta testing. If you are interested in playing around with it, send me a PM.

![poi-itunes-connect](https://s3.us-east-2.amazonaws.com/jarrodparkes.com/poi-itunes-connect.png "poi-itunes-connect")

All in all, this week was a big win because I got reacquainted with the app deployment process. Baby steps, right? In my next development sprint, maybe I will pick SKPokemon back up. Or, better yet, I might play with a game idea that will get me up-to-speed using Apple's Game Center! Either way, it will be fun!