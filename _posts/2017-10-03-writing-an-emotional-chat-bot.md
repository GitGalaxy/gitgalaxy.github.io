---
layout: post
author: jared
categories: [open-source, machine-learning]
date: 2017-10-03 05:33:34 +0000
title: Writing an "emotional" chat bot
image:
  feature: chatbot-banner.png
  teaser: chatbot-banner.png
---

<span style='font-size: 1.2em;'>A lot of things have changed since the beginning of computers.</span><br />

At first we used to type everything out in such a mechanical fashion -- in a way a computer could understand. The first "voice commands" couldn't understand you if you were off one or two words. But, in 2017, it's much different. Now you can phrase any question to Google Assistant and it'll understand you. Our only limitation is now how our voice sounds, even then that's only a minor problem. It's been said that the future of computing is via chat bots. Interfaces where you can type, or say, what you want done and it'll get done. A lot of these advances are thanks to, in part, machine learning. The process of getting a machine to *teach itself* the outcome of actions, via repetitive training or positive / negative feedback. Thanks to this, we can have machines learn, in real time, from our responses.

I recently set out on creating a chat bot that could interact with humans on an emotional level, something I haven't seen done before. Sometimes people just want to vent to someone about something, receive positive reinforcement, or even have an intelligent conversation. Now, not everyone is a super smart data scientist who thinks in calculus all day. Okay, maybe you are, but I know I'm not. Thankfully npm, the Node.js package management system, has tons of machine learning frameworks. In my case I've used a natural language processing library, as well as a sentiment analysis library. What is sentiment analysis? Well, sentiment analysis is a way of determining if a word is positive or negative. This is useful for measuring how a sentence can be taken, but it's not perfect.

**What's important for 'human' interaction?** That's the first thing you have to ask yourself when designing a chat bot. This is the most important part. Nobody wants to have to reword what they're saying just to make a computer understand it. You don't want to click a button, just to find out you didn't click it *just* long enough, and end up having to figure out how to do it right. No, we want to feel like we're interacting with another person. So, that means we have to be emotional. We have to have reasoning behind decisions, and we need to have natural language. Not the same thing over and over again. But, at the same time, it has to serve a purpose. Even if that purpose is just positive reinforcement. It has to do *something*.

That's the goal behind the bot I've been working on, while it's not currently intelligent, it'll eventually learn based off of user input as well as automatic training. If you take a set of certain social cues, you can determine if you've done something right or wrong. Such as, "K" isn't the same as "okay, sounds good!". Structure of words can tell you everything about how someone perceived something. This, however, presents the problem that every person is unique. Not everyone responds to things the same way. Though, using a series of set "tests", we can figure out how someone responds based on their emotional state at the time.

Part of why I decided to write a bot like this, is that I've struggled with Aspergers all my life. I have had to teach myself how to understand and process my own, and others, emotions. I don't always get it right, but over time I've been able to slowly get better at socializing when it comes to emotions.

If I can teach myself how to be 'emotional', maybe, just maybe, I can get a bot to do the same.


**Follow my bot on Github: [jaredallard/shinojs](https://github.com/jaredallard/shinojs)**