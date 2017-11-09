---
layout: post
author: gabriel
categories: [companies-open-source, walmart]
date: 2017-08-25 15:48:39 +0000
title: 'Companies Open Source: Walmart'
---

Companies Open Source is a series where we explore projects from large companies
that have been open sourced.

Walmart is an absolute juggarnaut in the consumer world, with stores selling
everything from clothing to produce to televisions to outdoor supplies. As such,
they need an infrastructure that is able to handle massive amounts of traffic,
either using their online store or using their in-store companion app. They've
graciously open sourced quite a bit of their backend and frontend, such as
electrode and thorax, under open source friendly licenses. Their open source
initiative is named Walmart Labs, and it's fascinating to explore.

One of Walmarts largest projects is "electrode", a JavaScript framework for
building large and small scale projects and "focuses on performance, component
reusability, and simple deployment to multiple cloud providers—so you can focus
on what makes your app unique" (from their README
[https://github.com/electrode-io/electrode/blob/master/README.md]). This is the
underlying framework behind Walmart.com [http://Walmart.com], and is incredibly
powerful and fully featured, including things like built-in above-the-fold
rendering (only renders components you can actually see on screen), stateless
CSRF validation, and a built-in asynchronous router that couples with React,
through the modules that you can add on to your project. It's open sourced under
the Apache 2.0 [https://choosealicense.com/licenses/apache-2.0/]  license.

Thorax is a frontend framework that combines Handlebars and Backbone into a neat
little package. Unfortunately the project's GitHub pulse doesn't seem to report
much activity, however on the surface it's an interesting idea, feeling like a
competitor to React or Vue.js. While Vue.js and React have taken over (although
React might loose favour after their licensing kerfuffle). While it's
unfortunate that the project has been discontinued (their website doesn't even
resolve), it's cool to see some earlier open source work by the developers over
at Walmart.

One project that I have personally been drawn to is active-status, a CLI tool
written in Clojure that shows real-time output of asynchronous console commands,
such as during a database migration.

 
[https://raw.githubusercontent.com/walmartlabs/active-status/master/images/db-migrate.gif]
via walmartlabs/active-status

While it won't magically work with existing programs, any tools that implement
active-status will be able to show the progress of several actions executing at
the same time, all without needing to scroll through. Unfortunately, this
project seems to be on the verge of going the way of the dodo, with the last
commit being to the clojurescript  branch about a month ago. That said,
funcationally it should be completely stable, and I look forward to learning
clojurescript, either to implement this into an existing project or contribute
to the repository.

There are several more projects open sourced on the WalmartLabs
[https://github.com/walmartlabs/]  Github organization, a large percentage using
JavaScript - not including electrode, that's it's own team
[https://github.com/electrode-io/]  - Objective-C, and Clojurescript, with some
miscelanous ones using Go and other languages. I'd highly recommend taking a
wander into some of the repositories and seeing what such an enterprise as
Walmart uses for their tech stack to power their mobile apps and online store.