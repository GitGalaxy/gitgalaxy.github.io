---
layout: post
author: gabriel
date: 2017-11-11
categories: story
tags: [github, open-source, stack, readme]
title: Moving to GitHub Pages
---

**So** you may have noticed some downtime recently, after the publishing of our
[open letter](https://gist.github.com/gmemstr/d5f493bbf92978dacd6eeb5f131e5541),
and defiently notice the change of design. You can check that letter out
for more details on this decision, but I want to go into some of the details
and the experience of moving to GitHub Pages.

The first hurdle to get over was getting our posts off of our Ghost droplet and 
into markdown files for Jekyll. This also comes in handy for archiving posts. Initial
attempts to use the export method built into the Ghost admin interface proved frusturating - there
was a lot of garbage that wasn't needed, and the "plaintext" entries were actually just HTML.
Thus, another solution had to be found, and I happened upon a gist by Marians which
accomplished this very thing (I had to make a few tweaks to match with the latest
database layout, which you can find [here](https://gist.github.com/gmemstr/0008acc9037dabafcf9f838f7018e5fd0)).
This worked fantastically, and formatted the markdown files for Jekyll blogs, but required
a bit of setup on the server itself (why is pip never installed _with_ Python?). In the end,
we ended up with all of our posts exported, with only a few things missing (AdSense code has
been stripped, and links have been weirdly misformated).

Next was the Jekyll theme to use. I actually picked this out before grabbing the posts,
because I wanted to find something that would look great before deciding between Medium and
GitHub Pages. This took a lot of time, but I settled on [Lagrange](https://github.com/LeNPaul/Lagrange),
because it looked very clean, had pagination, and also looked like it had a ton of potential
for modifications later on down the line. We'll eventually roll these out, over time (and of course
you can always make a pull request either to this repository or [my branch](https://github.com/gmemstr/Lagrange/)).

And so you might assume that this was all done, off to the races we go! But alas, not so; there were still
a few things to attent to. Specifically, the theme. I'd picked this theme because of the aforementioned
reasons, but when it came time to test it locally, I hit a few snags. First, it came without a Gemfile,
which meant I had to manually install the dependencies. Not a particularily big deal, as Jekyll is 
good with telling you what you're missing. But the second roadbump I came to was the pagination plugin,
`jekyll-paginate`, refused to work. Scratching my head, I couldn't find any sort of solution, and
instead went ahead and replaced it with `jekyll-paginate-v2`, since from the looks of things
the original plugin had not been updated in quite a while. After a couple tweaks, it worked fine but
when trying to deploy it to GitHub Pages, the pagination broke again. As it turns out, GH Pages
has a small selection of supported plugins, with no option to install custom ones, and thus it
was back to figuring out why the original plugin didn't work. I look high and low, and eventually managed
to find the solution. Turns out, when Jekyll generates a site, it dumps an almost empty `index.md` file,
which claims it can be ignored. This was the root of the problem. From the Jekyll website:

> Pagination does not work from within Markdown or Textile files from your Jekyll site. Pagination works when called from within the HTML file, named index.html, which optionally may reside in and produce pagination from within a subdirectory, via the paginate_path configuration value. 

Ah, jackpot. All I had to do is rename `index.md` to `index.html`, make sure the layout was properly set to the homepage,
and it worked.

Along the way, I had forked the theme and started making commits along the way, as I tried to track
down the issue. While I made quite a few commits, the majority of them ended up being reverted when
I found out my mistake, and the pull request had (thankfully) not been merged yet.

So another speedbump I hit was trying to get the domain name and SSL configured properly. Initially I
believed it would be as easy as adding the CNAME file, pointing the domain to GitHub's servers,
and everything would be peachy. Alas, this was not so. As it turns out, GitHub Pages doesn't support
HTTPS with custom domains, which is somewhat unfortunate, so for the time being that has been disabled.
We'll have to revist this at a later date. We've also switched to using CloudFlare for our DNS, as
we wanted stricter caching and had hoped it would be able to act as a medium to cover HTTPS.
Turns out this is not the case, but we'll look at it later down the line.

We continue our mission of covering cool open source initiatives and projects, and will take
advantage of GitHub Pages. As of now, we have no plans to migrate off, but thanks to Jekyll
if we do it's likely the transition will be seamless. And because of the change, you can 
more easily [contribute](https://gitgalaxy.github.io/menu/contribute.html), which is a huge
bonus.

<small>Also, a sidenote. We will continue to run ads on select, "feature" posts. This is
done so we can hopefully bring in and pay other professional writers for their writing,
and to funnel back into the open source community. We'd love to make this our
full time jobs, but ensuring a strong community is more important in the long run.</small>