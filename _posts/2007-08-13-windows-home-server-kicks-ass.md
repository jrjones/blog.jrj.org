---
layout: post
title: Windows Home Server Kicks Ass
date: 2007-08-13 11:40
author: jrj
comments: false
tags: [Backup, Network Infrastructure, Servers, Technology, WHS]
category: Technology
---
The other day, Rachel came to me with a seemingly simple problem... her hard drive on her laptop was full. The last time this happened it was because we had recently subscribed to the MTV “Urge” service and she had proceeded to download a couple hundred gigabytes of music. However, this time it wasn’t so simple.

When I took a look at the drive, it showed that about 158 gigabytes of her 160 gigabyte drive was full. Simple, right? The problem is that when I dug deeper, there was only about 80 gig on the drive... the rest of the space was incorrectly reporting as allocated despite not having any data on it.

I ran chkdsk /r, which had no impact, but confirmed my suspicion that the drive was reporting unallocated space as being allocated. At this point, I could have spent a bunch of time troubleshooting, but I figured it would be easier to just blow the machine away.

I popped in my Windows Home Server restore CD, and rebooted the machine. It went to the nice GUI recovery console, found the WHS server on the network, and gave me a chance to select one of the nightly backups. Since one had occurred last night a little after midnight, I selected that one. It formatted the hard drive, and restored all Rachel’s data, applications, OS, and settings to exactly the way they were last night, except without the allocation problem. Perfect.

If it had been a virus, or other issue, I could have restored the PC to the exact state it was a week ago or more. This saved me a ton of time troubleshooting. Instead of spending an indeterminate amount of time trying to figure out what the problem is, I spent 10 minutes booting from a recovery CD and an hour and a half later the PC was back up and running without a problem. This is good stuff.

This is the first time I’ve had a reason to use the restoration functionality of WHS, and I was pleased with how simple the process was. This is a really exciting product.
