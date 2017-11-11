---
layout: post
author: gabriel
layout: post
categories: opinion
tags: [javascript, frameworks, open-source]
date: 2017-10-17 14:00:00 +0000
title: Changing My View of Frameworks
---
JavaScript frameworks tout features like making it "painless to create interactive UIs" and being "Approachable", so why have I held off learning one for so long?

For the longest time now, I have been a huge supporter of avoiding frameworks, especially frontend JavaScript libraries, in favour of writing everything as close to "bare metal" (as close to bare metal as you can get with JavaScript) as possible. But after investing a bit of my time into learning Vue.js, I've started to sing a different tune, especially since I've had the opportunity to put it into practice.

In the beginning, what scared me off of frameworks the most was React. Admittedly, I was a much more novice developer, but that didn't stop me trying to dive head first into the world of frameworks, straight into the most popular. I initially tested the waters with a couple scattershot projects, but didn't really try until I decided to revamp the NodeMC dashboard using React. It actually went okay, and I got some of the basics done (see the [v6](https://github.com/nodemc/dashboard/tree/v6) branch). Unfortunately I went too fast, flew too close to the sun if you will, and lost interest, trying to spread myself too thin by looking into how to build it as a mobile app, while also trying to learn the new ES6 CORE codebase thanks to Jared's rewrite. Regardless of the circumstances, I somehow instated in my head that frameworks were too much of a hassle, especially considering that the previous dashboard I had functioned perfectly anyways.

And thus I continued, ignorant to the advantages of frameworks. Don't get me wrong, I did occasionally go back and give it a shot, but once words like TypeScript and Babel started getting thrown around I quickly put it down. I was stubborn and assumed _all_ frameworks _must_ be like React. I continued to write code [like this](https://github.com/gmemstr/pogo/blob/4dd25948f614556d1b8a586387a2e448a4b5fca1/assets/web/index.html#L51-L61) (yes, this is currently in Pogo!), and openly talked about how useless I believed JavaScript frameworks were, adding in unnecessary bulk to do the same things you could with normal JS, but more difficult. Why bother with TypeScript and Babel?

As it turns out, I didn't need to. Recently for Pogo I wanted a straightforward multi-page admin interface, for things such as editing episodes, publishing and editing the CSS. I'd noticed Matthew had started to work with Vue.js, moving the NodeMC dashboard to that, and decided to take a stab at it myself. It _looked_ pretty straightforward, not calling for many dependencies besides itself, which was exactly what I wanted. And after moving the admin interface to it, I definitely see the value of frameworks now. No longer do I need multiple HTML documents for the admin interface, nor "complex" JavaScript for smoothly handing single-page apps. I'm loving this new experience, and can't believe I held off so long.

The advantages of using a JavaScript framework depend heavily on which one you choose. In the case of Vue.js, I wanted two things. Very simple dependencies and a good router system for a single page app, both of which are available under Vue's roof. There are no dependencies on Babel or TypeScript, you don't need to play around with webpack or npm, and importantly, it's pretty simple. A lot of the work is done with the JavaScript, deciding what to show and hide, what data to put where, and so on, but it doesn't _force_ you to put absolutely everything into your app.js. CSS can still be applied normally, as can any elements on the page that don't need to change.

Regardless of your personal stance on frameworks, I encourage everyone to give Vue.js a chance, or whichever framework we're talking about next week. You don't have to immediately jump onto the React train, because some may find it overwhelming, as I did, and completely turn themselves off on the idea of frameworks. It's important to start small, not necessarily with whatever is the most popular thing out there.