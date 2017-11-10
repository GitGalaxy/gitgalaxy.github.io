---
layout: post
author: gabriel
categories: [readme, podcast]
date: 2017-07-11 19:47:36 +0000
title: Podcast Update!
---

Hello!

  ![](https://i.imgur.com/w5u4Rzq.png)

So, it's been a little while since the last update, and in that time I've made
some fairly decent progress on fully testing White Rabbit. While I am still
scratching my head over how to implement iTunes-specific XML tags into the
gorilla/feeds library, I've gone ahead and deployed it to a Droplet. It's a
small, 512MB VPS (the original goal was to have it run on the same server as
this Ghost blog but thanks to some Ghost/nginx/Let's Encrypt snafu that's not
possible) that runs the software wonderfully (granted, it's pretty minimal).

Deployment is still difficult at this point. It requires an install of Golang
1.8 (I did this in Ubuntu via snap install --classic go) and some manual file
creation, namely the podcasts/  directory. It's also advantageous to touch
feed.rss feed.json  if you don't immediately upload an episode. You also need to
do a couple go gets.

```
get get github.com/gmemstr/feeds
get get github.com/spf13/viper
get get github.com/gorilla/mux
get get github.com/fsnotify/fsnotify
```

and then

```
go build webserver.go generate_rss.go
./webserver
```

But it does work, for the most part. It will freak out if you upload an mp3
without shownotes, and files need to be named in a specific format (by design,
although with the admin interface you won't need to worry as much), which is 
YYYY-MM-DD_TITLE NAME.mp3. Shownotes are YYYY-MM-DD_TITLE NAME_SHOWNOTES.md.
Convoluted, a little bit, but it's still being worked on, and again, once the
admin/publish interface is done this won't be such a glaring issue.

In the end, you'll have a couple options - a raw RSS and JSON feed to pick from,
and a basic frontend that allows you to see the shownotes and play back
episodes. It's super basic as of right now but it's functional for debugging.

I'll be writing up a larger piece about my experience creating this software in
the future, but I wanted to let you know that the basic CMS is currently online
at [podcast.gitgalaxy.com](https://podcast.gitgalaxy.com). Feedback is very much
welcome at our new email contact@gitgalaxy.com. Any general questions or
comments can be directed there, and any White Rabbit specific questions should
be directed to gabriel@gitgalaxy.com. Issues should be opened on [GitHub](https://github.com/gmemstr/whiterabbit/).