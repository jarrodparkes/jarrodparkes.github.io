---
layout: post
title:  App Script for Google Docs
date:   2016-02-13 08:40:30-0600
tags:   rss
---

My latest programming project lead me to write a Google Apps Script (GAS). The first thing I will say about GAS is that the documentation is a little rough, but if you stick with it, you can build some powerful add-ons to Google Docs and Sheets. To start building a GAS, open a new Google Doc or Sheet and select `Tools` --> `Script editor...`. This will launch a light development environment where you can write, test, and debug your GAS.

A few caveats that I should mention before you get started:

- Collaboratively working on GAS is a nightmare, there is no built-in support for doing distributed work with multiple people
- GAS have different types of deployment models... in this post, I am referring exclusively to GAS that are add-ons
- While you are building an add-on it is coupled directly with either an individual Doc or Sheet; once you deploy an add-on it can be connected to many documents
- The GAS editor allows you test server-side functionality directly (this is a really feature!)

With that out of the way, you can get down to business. The "add-on architecture" is typically separated into two parts: (1) client-side code and (2) server-side code.

### Client-Side Code

For most add-ons, you will create some HTML that gets displayed either as a dialog or a sidebar. In either case, this HTML can include Javascript which has it own special functionality. In my case, the Javascript calls back to the server so that it can manipulate the Google Doc itself.

### Server-Side Code

The server-side code is where you have the ability to modify the contents of the Google Doc (or Sheet).
