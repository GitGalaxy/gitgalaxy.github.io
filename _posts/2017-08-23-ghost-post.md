---
layout: post
author: gabriel
categories: [ghost-tag, open-source]
date: 2017-08-23 01:20:05 +0000
title: Ghost
---

It should come as no surprise that this website is built upon the Ghost blogging
platform, a kickstarted project that was hugely successful, and continues to
grow.

Since it's inception, there have been over 7,000 commits to their Github
repository, with people writing hundreds if not thousands of lines of JavaScript
that helps power this website, along with several other notable blogs, such as
Square's Townhouse and OpenAI's website. They've had over 100 releases tagged on
Github, and power over 1.2 million blogs.

Impressive numbers, and they've certaintly come a long way - way back in the
days of their alpha releases, there was a lot of manual installation to be done
- cloning the repository (or downloading a release), editing config files,
setting up Nginx, and setting daemon configuration. And now, the setup is as
simple as installing Node.js, doing an install of their CLI tool (npm install -g
ghost-cli), and running the command.

Upgrading was easy as well - at least, in our case. We were on a version prior
to v0.11.0 (thanks DigitalOcean), however all that was required was an update to
Node.js, installing the CLI tool, exporting the configuration via the admin
interface, and then setting up a new blog from scratch.

Initially, Ghost was a project on Kickstarter, which was created by John
O'Nolan. He was a well known developer in the CMS space, creating blogs for
several larger companies and eventually becoming head of UI at Wordpress, and
currently travels the world and simultaneously runs Ghost. We reached out to him
on how he manages to do it and will update this post when we hear back.