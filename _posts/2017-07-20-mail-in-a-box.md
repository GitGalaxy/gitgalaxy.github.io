---
layout: post
author: gabriel
categories: []
date: 2017-07-20 07:29:00 +0000
title: Mail-in-a-box
---

Everything and probably the kitchen sink.
Many decisions have been made while setting up Git Galaxy, not least of all what
we should use for mail.

I first considered using Gmail, but I felt that looked less professional and was
much less flexible as well. I definitely wanted to host our own mailbox, because
past experiences with things like Zoho Mail left a bad taste in my mouth (the
interface for the most part). Manually installing and configuring packages
would've worked but also would have taken some time - not to mention we used a
"one-click app" from DigitalOcean (our referral!
[https://m.do.co/c/fb360f382c7e]) to deploy this blog, which means there's a lot
of configuration files that can be a bit tricky to navigate. This isn't a huge
issue if you're doing a standalone server, but if the goal was to have a couple
things on the server, you're going to do a lot of head scratching.

But I digress; the ideal solution, as I found out, was mail-in-a-box, an
all-in-one solution for setting up your own email server. It's not perfect, but
we'll get into that.



Setup was a breeze, but you need to specifically be on Ubuntu 14.04 x64 and at
least 1GB of RAM. Fortunately this wasn't an issue for us, but keep that in mind
if you choose to deploy this yourself. You need to setup your domains
nameservers to point to the box (we use namecheap so we used this guide here
[https://www.namecheap.com/support/knowledgebase/article.aspx/292/10/how-can-i-update-my-personal-nameservers-ip-address]
), and then you're ready to run the installation script. Typically it's not best
practice to run a curl piped to bash directly without verifying the script
you're running, so verify that the file is clean. You'll run through a setup
process that doesn't take very long, and once everything is good and dandy you
can load up the admin interface and go through the checklist.

I recommend reading through DigitalOcean's community guide here
[https://www.digitalocean.com/community/tutorials/how-to-run-your-own-mail-server-with-mail-in-a-box-on-ubuntu-14-04] 
 for full setup instructions.

Initially, upon loading the admin interface, you are greeted by the "System
Status Checks" page, which goes through your system and domain configuration to
make sure everything is pointing to where it should be, including nameserver and
DNS entries. From here you have a couple options, such as managing your Let's
Encrypt certificates, custom DNS entries for pointing your primary domain to
another server, configuration of your email accounts, including aliases, and so
on. It's not the prettiest, most modern design, but it does get the job done so
no complaints.

Mail-in-a-box comes with a few additional things besides the mail server. You
have the DNS, which is almost essential for setting up the server. It is
possible to not use the nameservers that point towards, however when I attempted
this is turned out there are a lot  of entries you need to manually add. There
is a built-in nginx webserver, which I opted to throw an index.html file into
that just redirects to mail. It also comes with calendar and contacts storage
with Nextcloud, which is a nice touch I have yet to personally use.

So with that out of the way, let's take a look at the code that handles all the
setup. The project is open source over at mail-in-a-box/mailinabox
[https://github.com/mail-in-a-box/mailinabox], and is a mix of Python and Bash
(or "Shell"). The bash portion is found largely in the setup portion of the
application, however there are some bash scripts in the "management" folder,
which is for all intents and purposes Mail-in-a-box proper. If you're wondering
where the curl-to-bash setup script is, it's located in setup/bootstrap.sh
[https://github.com/mail-in-a-box/mailinabox/blob/master/setup/bootstrap.sh]. It
basically checks that it is running as superuser, double checks that git is
installed, then clones the repository, finishing up by firing the setup/start.sh
[https://github.com/mail-in-a-box/mailinabox/blob/master/setup/start.sh] 
script. Overall, code quality looks excellent - everything is carefully
commented, and is all very readable. An interesting note, the "management
daemon" (the collection of Python scripts responsible for the web interface) is
using Flask as a webserver (management/daemon.py
[https://github.com/mail-in-a-box/mailinabox/blob/master/management/daemon.py]),
an excellent choice for such a project.

So far, the results we've experienced have been more than satisfactory, and I
would definitely recommend the project to anyone looking to set up their own
mail server easily, with options to self host contacts and calendars, and have a
webpage hosted on the same server if need be. The downside is that your entire
machine becomes dedicated to Mail-in-a-box, with little option to expand or host
other apps from the same machine. Playing with glue records for the first time
can be intimidating, but it does handle all the DNS entries required to have a
solid email server. By default it installs Roundcube as a client, but I have
found myself, for the first time ever, properly using Thunderbird. Adding it as
an account is fairly easy, and the same can be said when adding it to the Gmail
app on Android.

If I gave scores, Mail-in-a-box would be at least a 9/10 for ease of use,
simplicity, development standards and learning potential. It might seem a bit
overwhelming, or bloated, bundling in Nextcloud during the installation, but the
pros outweigh the cons a significant amount.