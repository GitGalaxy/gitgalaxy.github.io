---
layout: post
author: gabriel
date: 2018-01-15
categories: story
tags: [pogo, building, story, backstory]
title: Building Pogo
---


It's been a while since I've made an effort to write a story for Git Galaxy. But we're picking up on a strong note - the background and story of [Pogo](https://github.com/gmemstr/pogo), a podcast feed platform I've been working on for the past eight or so months.

It began before Git Galaxy in it's current incantation, but pretty near enough the two are associated in my mind. I wanted to run Git Galaxy as a podcast first and written content second, and it's clear which one was easier to manage between school, family, everyday life and a job (which is no longer an issue but I digress). But in the initial stages of planning, I wanted to self host the feed and audio files - the latter being pretty straightforward, the other not so much. There were no good _lightweight_ options for hosting a listening front end on one's own servers. There was the option of using a WordPress plugin, but being averse to such complexity and potential security issues I left that alone. The other option was using a third party host like [libsyn](https://www.libsyn.com/) or the then recently released [PodSheets](https://www.podsheets.com/), but I wasn't content with letting another host keep hold of my precious audio, and in the case of downtime or unexpected shutdown it would be disastrous. There was also the question of cost versus scaling up storage space or bandwidth, which can be easier or cheaper with a self hosted option (with some added complexity admittedly).

### Basic Backend

So with all this in mind, it was time to get to work. There was the typical motivation in my choice of language (Go), being that of "I want to learn this hip, trendy new language", and some very rough first attempts. Eventually, I managed to make something fairly functional as a MVP, under the name of White Rabbit. You can check out the earliest code base committed [here](https://github.com/gmemstr/pogo/tree/e193e33678f8a93465174e9965b34f27f6015fd9). All it did was watch a folder named "podcasts" for changes, and used the `gorilla/feeds` library to make an RSS feed. Along the way I had to fork the feeds library to include useful podcast feed tags, such as `<enclosure>` and `<image>`, which eventually made their way into the parent repository ([PR](https://github.com/gorilla/feeds/pull/41)).

### Early Frontend

Early RSS feed creation out of the way, it was time to work on a frontend. You can follow my progress through [early commits](https://github.com/gmemstr/pogo/commits/master?after=6d1cadaac5223b2da53557bb6ab39887f01eddc8+174). Essentially, it needed two components - an interface for listening to episodes and reading descriptions, and an admin interface for publishing. After some preliminary investigation I added JSON feed generation and got to work with plain old JavaScript, which has actually gone largely untouched in the "DeV" front end (more on that later). The admin login relied on a plaintext (ew) password in the configuration, and HTTP's BASIC authentication method. It worked, with basic episode publishing and editing, but there was much more to do, including removing the fact that the admin password was stored in plaintext. Unfortunately, this wasn't fixed until much later by ishanjain28. Regardless, with a basic frontend, it worked fine. I believe this is around the time I tagged my first release, so it was time to add and refine features.

### Gearing up for 2.0

With version 2.0, I had a few goals in mind. First, rewriting the frontend in Vue.js - I had dabbled a bit with it for the admin "DeV" interface, and I found myself liking it quite a bit. The second feature I wanted to build out was a completely self-contained binary. While I could've found a way of bundling the frontend with the backend binary, I opted for the second option; download the release from GitHub when first run. Using this, I could also build in other "first run" features, such as the creation of the user database and generation of "missing" files. This would allow the first time setup but maintain the portability - when v1.2.0 was tagged I had moved to using an SQLite3 database for users, because JSON in Go can be a pain, so I freed up a lot of room for feature expansion and multiple users. This also allowed me to set up user permisions, gating off specific routes and functions, which was not originally planned but is a nice feature to have. With these goals in mind, I set out to get it done.

### The 2.0 Grind

About halfway through getting Pogo 2.0 done, I felt myself starting to run out of steam and forcing myself to get it done. A large amount of some more "core" features had been completed, permissions and user management were functional, and setup was almost done, but I found myself considering just tagging the release and giving up on the few remaining features and bugs I had to sqaush. Namely, configuration editing from the admin interface, which I had previously not included in 1.0 because that was where the password was stored. This changed in 1.2, but I held off any major route revisions. I managed to convince myself to not tag the release as 2.0 or even 1.3, and it frankly feels really worth it. Had I tagged another release, I was scared I would've felt this leg was "done" and I would take my leave as I am now.

There was also the frontend, which had been mostly ported over to Vue.js. While I liked what I had initially, it felt an upgrade to a SPA structure would help the project, and breaking the frontend into it's own repository had it's own perks (especially for the auto setup). I deprecated the old interface to what I've nicknamed "DeV", or "DEvelopers Version", which is still included in the GitHub repository for the time being. It's useful for development and debugging routes, but otherwise is not used for product. Having the dashboard as it's own thing will also open the chance for the frontend to auto update (although I'm more on the side of keeping it open for other people to develop their frontends).

Regardless, 2.0 felt like a grind nearing the end, and commits slowed down a bit. You can see the big project checklist [here](https://github.com/gmemstr/pogo/projects/1). I wish I could graph the frequency of these updates, but it wasn't quick. Unfortunately this also lead to my current feeling of burnout (specifically code-wise, clearly, over 1100 words in this post).

### Where Pogo is now

Pogo v2.0.0 is done and out, with a very viable structure and (in my opinion) pretty nice code. It's not perfect, and a lot of the work that will go into the first minor patch will be code cleanup and commenting, but it's a) stable and b) has all the major features one would need. While I am still hesitant to dedicate myself to the audio portion of Git Galaxy, at least I know it's entirely possible and easy to get it going. I'm going to be taking an extended break from Pogo in the meantime, working on promotion and documentation but leaving the code alone - I want to move on to another project.