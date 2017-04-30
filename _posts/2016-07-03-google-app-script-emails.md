---
layout: post
title:  Google App Script Emails
date:   2016-07-03 11:36:00-0600
tags:	google
---

Google App Scripts,

*Where were you during college when I used Google Documents and Google Sheets for everything? How could I have overlooked your mystical powers? Your abilities to perform complex transformations, generate boilerplate material, and improve my workflows?*

But, the past is the past. Let’s get started on the right foot… with a plan and a solution.

The plan I have in mind involves sending automated emails at regular intervals. The solution involves utilizing **MailApp service** and **project triggers**. So, how about it? I am assuming, of course, you know [how to get started](https://developers.google.com/apps-script/overview).

## MailApp Service

For us to send an email, we must use the [MailApp class](https://developers.google.com/apps-script/reference/mail/mail-app). This class provides methods for sending emails with varying levels of configurability. For our purposes, we’ll just use the most straight-forward version of the `sendEmail` method that takes a receipt, subject, and body:

```javascript
sendEmail("recipient", "subject", "body");
```

We could call this method as follows…

```javascript
sendEmail("name@email.com", "Say Hello", "Hello, how are you? This is an automated email from my Google Sheet.");
```

Now to add a little sophistication (and automation) to our emails with project triggers.

## Project Triggers

Project triggers, which are a class of [installable triggers](https://developers.google.com/apps-script/guides/triggers/installable), allow us to call user-defined functions at regular intervals. So, have a method for sending an email? We can send it every hour or every day or… whatever your heart desires. But first, we’ll need to define a function:

```javascript
function sendEmail() {
    sendEmail("name@email.com", "Say Hello", "Hello, how are you? This is an automated email from my Google Sheet.");
}
```

With the function in place, all we have to do is configure a few settings using the **Current project’s triggers** dialog found in the **Resources** tab. If we wanted to call this function every day around 3:00 a.m. - 4:00 a.m., then we could use the following settings:

![Google App Script - Project Triggers](https://github.com/jarrodparkes/images/blob/master/gas-project-triggers.png?raw=true "Project Triggers")

And, that’s it! Now, the project trigger will automatically send an email (using our function) at a regular interval.

This is going to be really fun... I’m really looking forward to getting to know each other better.

Your friend,

Jarrod
