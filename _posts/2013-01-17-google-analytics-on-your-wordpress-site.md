---
layout: post
title: Analytics on WordPress Site
date: 2013-01-17 
tags: web
---

![google-analytics](https://s3.us-east-2.amazonaws.com/jarrodparkes.com/google-analytics.png "Google Analytics")

Google Analytics is a robust web platform for tracking usage statistics, traffic, and many other demographics on websites. After speaking with a coworker about Google Analytics, I decided to take a look at the product myself.

To test Google Analytics, I used one of my WordPress sites, but any site would do. I was pleasantly surprised to find that adding Google Analytics to a WordPress site only required a few simple steps.

1. Register your WordPress site by visiting [Google Analytics](http://www.google.com/analytics)
2. Navigate in the admin section of your WordPress site to *Appearance --> Editor*
3. Once you are at the editor page for your theme, find the PHP file dubbed "header.php"
4. Copy and paste the Javascript tracking code from your Google Analytics dashboard somewhere within the <header> </header> HTML tags

You can find the tracking code under "Tracking Info" in the Admin section. Look for the JavaScript icon. Here is a copy of my snippet with the Tracking ID number boxed out.

![google-analytics-tracking-code](https://s3.us-east-2.amazonaws.com/jarrodparkes.com/google-analytics-tracking-code.png "Google Analytics Tracking Code")

If your site does not use WordPress, adding the Google Analytics tracking code is still very straightforward. Assuming your site is dynamically generated using a server-side scripting language, just copy and paste the tracking code into a source file that get embedded in the &lt;header&gt; section of every page on your site. For most cases, the source file will probably be named something like "header.{file-extension}", but if not, you can always create your own.

Beyond my example, the Google Analytics framework also supports many different custom settings, reports, and configurations. For example, you can embed tracking into websites where the design is only one page. Thus, you can treat anchors within a page like they are their own separate pages with their own tracking.

If you have never used this tool before, I highly encourage you to add it to your websites.