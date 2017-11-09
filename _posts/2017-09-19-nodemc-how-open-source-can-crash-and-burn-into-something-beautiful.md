---
layout: post
author: jared
categories: [open-source, nodemc]
date: 2017-09-19 04:00:36 +0000
title: 'NodeMC: How Open Source Can Crash and Burn Into Something Beautiful'
---

Minecraft, almost everyone has heard of it.  It started out as a small indie
game, and has since then become one of the best selling games of all time. Kids
are fascinated with it, adults are ashamed to admit that they still play it.
Regardless, one has to admit that it's been a prime influence on society today.
One that doesn't appear to be going away.

Behind this large sensation, are people who spend their lives running and
maintaining servers that people play on. With this comes the need for a lot of
resources and smart people to handle all of that load. Usually this is done with
the help of open source tools, Facebook uses them, with Hack
[https://code.facebook.com/posts/264544830379293/hack-a-new-programming-language-for-hhvm/]
, and tons of other companies contribute and create their own open source
software. The world is powered  by it. Minecraft server maintainers haven't
really had an free/open source (FOSS) server hosting solution. That's where 
NodeMC [https://nodemc.space]  came in. NodeMC started of as a small project
created by our own, Gabriel Simmer [https://gitgalaxy.com/author/gabriel], in
early 2016. Initially it was a monolithic stack, that worked, but had some
issues. I came in around mid-2016 and completely rewrote it from the ground up
with the help of Mathew [https://github.com/md678685]. The project, while
neither very stable or mature, received a ton of natural attention. It became
clear to us that the project was hitting a field that desperately  needed it.

Fast forward to early 2017, and unfortunately the project fell apart. Neither I,
nor Gabriel, had the time to continue maintaining the project. This led to a
backlog of potential users' issues. Keeping motivation to run an open source
project has always been a problem. Typically open source developers don't get
paid for their work, but are expected to keep their 'product' in a production
grade state. Those two don't quite work together, imagine being asked to come
into work, working just as hard as you always do, but you're not getting paid.
Not very appealing. Open source highlights the best of devs, and their love for
what they do. I've been contributing to open source software for just over 5
years now, and I've loved working on every commit I've pushed so far. It's more
than just a hobby, it's a way of life. Eventually Gabriel ended up leaving the
project due to time constraints, so I became the new maintainer



It's shocking how becoming a maintainer can make you quickly change an entire
project. First it started with redesigning the API, and quickly turned into an
entire architecture change and re-scoping of the project. Instead of being
focused just on one server, I realized we could turn this into a orchestration
platform that would bring resilience to the table. Running the DevOps team at 
StayMarta [https://staymarta.com], has taught me invaluable knowledge about how
to take a small application and make it scale properly. Too many companies
develop a MVP and have issues down the line making it handle all their users,
however, at StayMarta we're prepared for anything. We can spin instances up and
down on a whim, without any issues. It's one step away from running itself. I've
brought this skill set with me to NodeMC, and plan to make it just as reliable
and scalable as I've done there.

In the end NodeMC will go from a half-baked idea, to a mature, dependable
platform that people can count on and build things with. That's why we have an
openly documented API [https://github.com/NodeMC/CORE/tree/master/docs], for
developers, it can run on any Linux-based server, and is completely self-hosted
with limited technical support for all bugs on Github. Expect to see NodeMC
mature rapidly and maybe even watch over your favorite Minecraft server soon.
Until next time.

If you found this project interesting, feel free to follow NodeMC on Twitter
[https://twitter.com/BuiltWithNodeMC]  or contribute to it on Github
[https://github.com/NodeMC]!