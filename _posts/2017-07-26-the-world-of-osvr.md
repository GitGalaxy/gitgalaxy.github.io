---
layout: post
author: nathan
categories: [osvr, virtual-reality]
date: 2017-07-26 03:17:00 +0000
title: The World of Open-Source Virtual Reality
---

Virtual reality is a topic that has seriously interested me in 2017. Although we
constantly hear about the “death of VR”, I have faith that VR is the future of
technology to some degree. It might take decades and we probably won’t be
ditching our normal lives for the a virtual one, but VR has an unbelievable
potential to take off. Now, VR offerings are decent these days, ranging from the
makeshift Google Cardboard to high-power HTC Vive. However, I’ll be focusing on
OSVR (Open-Source Virtual Reality) for the purpose of this article.

Backed by Razer and Sensics, the OSVR project aims to create an interchangeable
system for VR hardware and software components alike. It encompasses hundreds of
HMDs, controllers, and other peripherals to bring together hardware under one
common roof. The software platform works similarly, supporting several operating
systems and game engines. OSVR gives developers freedom in the VR space and
essentially serves as a dev kit with a wealth of customization. In essence, OSVR
is built with developers in mind, but provides a few benefits which may interest
the average consumer too.

In regards to central hardware, OSVR exists as a head-mounted display called the
HDK (Hacker Development Kit). It costs about $500 at the moment and boasts specs
up to par with the leading HMDs in the market. With a 2160 x 1200 dual display
at 90 Hz, 110° field of view, and 8x9 feet tracking zone, the HDK does not
disappoint.[1]  For this reason, it may appeal to both developers and VR
enthusiasts alike. Furthermore, it’s compatible with all these VR devices
[https://osvr.github.io/compatibility/]. The real drawback here is that
operating OSVR requires a knack for technical troubleshooting and setup. It’s
generally unpolished and isn’t meant to serve as a perfect VR experience, but a
way to tinker with different modules and configurations. You’re bound to
encounter several cumbersome issues when working with the HDK which all come at
the price of being open-source. Note that image stutter, distorted edges,
startup crashes, uncomfortable nose support, and graphic driver issues have been
specifically reported by HDK 2 reviewers on a regular basis.[2]

On the software side, OSVR blurs the line between assorted devices and
applications in order to make it easier on developers. The OSVR core is written
in C++ but repository activity has definitely slowed down considerably in 2017
compared to years past. The system allows devs to choose their preferred tools,
both physically and digitally, without any real difficulties. It also allows for
various plugins to be implemented such as eye or gesture tracking
[https://github.com/OSVR/OSVR-SMI]. Several of these plugins are open-source as
well, allowing for further expansion on the OSVR modular ecosystem. Lastly, it’s
all free to use and under the Apache 2.0 License, which allows for both
modification and distribution. OSVR is so appealing because it also works with
every major game engine like Unity, Unreal, and even SteamVR with custom
support. Integrating these engines is relatively simple and opens the gates to
unrestricted VR game experimentation.

There aren’t really any other companies working on something similar to OSVR
other than Valve. In collaboration with OSVR, Valve is developing a similar
system called OpenVR. This software development kit works alongside SteamVR to
provide some additional optimization and freedom. Generally speaking though,
OSVR can be considered the only major open-source VR development setup out
there.

Although OSVR has lost some traction in recent months, the future still looks
very bright. Razer continues to fund OSVR with millions of dollars and the HDK
has been out for a couple years now.[3]  Every day, the applications and
commitments to VR increase thanks to projects such as OSVR. An open-source
option in the VR market breaks some boundaries and keeps development moving
steadily ahead in a technology that may completely change the game.


--------------------------------------------------------------------------------

 1. OSVR Specs: http://www.osvr.org/hdk2.html  ↩︎
    
    
 2. Reddit: Some input from HDK 2 users
    [https://www.reddit.com/r/OSVR/comments/4ydpb0/would_you_recommend_buying_the_hdk_2/] 
     ↩︎
    
    
 3. Razer's OSVR Investment: 
    https://www.roadtovr.com/razer-5-million-osvr-developer-fund-investment/  ↩︎