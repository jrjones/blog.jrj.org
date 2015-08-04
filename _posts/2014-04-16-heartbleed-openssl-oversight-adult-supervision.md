---
layout: post
title: Heartbleed Shows a Need for Oversight
date: 2014-04-16 18:49
author: jrj
tags: [heartbleed, Open Source, openssl, security, SSL/TLS]
category: security
excerpt: "Hearbleed demonstrated projects critical to the net’s infrastructure need help…"
headerimg: heartbleed.png
---
<!---
![Hearbleed Vulnerability](/assets/postheads/heartbleed.png "Heartbleed OpenSSL Vulnerability")
-->

Heartbleed happened while I was on my vacation and not really keeping up with things, hence I haven't really commented much. [Dan Kaminsky (and, by extension, Matthew Green) pretty much summed up my thoughts perfectly][1]:

> "...The answer is that we need to take Matthew Green’s advice, start getting serious about figuring out what software has become Critical Infrastructure to the global economy, and dedicating genuine resources to supporting that code."

**Exactly right.** We can't have fulcrum points of Internet infrastructure held together by chewing gum and bailing wire in the form of code written by hobbyists. When an open source project reaches a certain point of critical mass it requires professional oversight and rigorous security audits. Not to put too fine a point on it, but "adult supervision."

I'm not discounting the contribution of open source developers, nor am I minimizing the benefit of the transparency an open source model provides. I'm simply stating that it is not a full replacement for the input of security professionals and comprehensive audits. To some degree this can be crowd-funded (example: [TrueCrypt audit][2], though much more needs to be done here) but for the most critical components of internet infrastructure like Open SSL, the companies that benefit most need to pay a share. Oracle and Google are the first names that come to mind, but there are dozens of companies that could (and should) contribute to a consortium to work together to ensure the integrity of internet infrastructure. I usually don't blog about work, but I will say that if such a consortium existed I would advocate loudly inside Adobe to contribute, and I suspect that call would be met with enthusiasm. 

[Kaminsky's post][1] is a bit long, but very much worth reading.

[1]: http://dankaminsky.com/2014/04/10/heartbleed/
[2]: http://istruecryptauditedyet.com