---
layout: post
author: gabriel
categories: [open-source, github]
date: 2017-10-01 16:00:00 +0000
title: A Look at Hacktoberfest
image:
  feature: hacktoberfest-banner.png
  teaser: hacktoberfest-banner.png
---

DigitalOcean and Github have teamed up to encourage people to contribute to open source - but what exactly is "Hacktoberfest", and what does it mean for the larger Github community?

Let's talk about the two companies behind this. There's Github, the well known and massively popular git repository hosting platform on which the competition is being run, and DigitalOcean, a well known player in the virtual private server space. They have teamed up with one (well a few if you count marketing) goal in mind: Encouraging people to help out other open source projects. 

The way the fest is set up is pretty straightforward. You sign up [on their website](https://hacktoberfest.digitalocean.com/) by linking your Github account, then from October 1st to the 31st you need to make four pull requests to **any** Github-hosted repository (I've reached out to DigitalOcean to confirm they just have to be made, not accepted), and you will recieve a limited edition Hacktoberfest t-shirt. Contributions are not limited to issues tagged "hacktoberfest", and absolutely anyone with a Github account can get signed up regardless of how old the account is. 

Now that we have that out of the way (please take a look at the website or tweet DigitalOcean for more info), let's analyze some of the affects that this Hacktoberfest seems to have had on the community.

First, let's use the suggested search query the website provides us for Github. [label:hacktoberfest state:open type:issue](https://github.com/search?l=Go&q=label%3Ahacktoberfest+state%3Aopen+type%3Aissue&type=Issues) will search repositories for open issues with the tag hacktoberfest, just to make filtering and discovery a little easier. Here, we can get a general sense of the sort of audience jumping on to this hackathon just by looking at the languages offered up in the side bar - at the time of writing (one day before requests start to count), we see JavaScript dominating this list, with nearly twice the number as the next language, Python. This reflects the state of JavaScript quite clearly, with Node.js, Electron and ES6 bringing about an absolutely enourmous surge in popularity to the language, and clearly people have a lot of projects that they would like help with. 

An interesting note about some of the behaviour I've seen - a few projects are very barebones, some still figuring out there stack, creating issues to implement things that seem pretty mission critical to the underlying application. This isn't neccesarily a bad thing - the goal of the hackathon is to encourage people to reach out and help with projects - but it's interesting to observe that people assume, and rightly so, tagging issues with hacktoberfest will help them be surfaced and placed in front of other users. 

I will most likely update this post when Hacktoberfest is over and I can reach out to DigitalOcean to hopefully gather some stats, but it's been interesting to observe the traction and activity that has taken place, and the reflection of industry trends in regards to language adoption.