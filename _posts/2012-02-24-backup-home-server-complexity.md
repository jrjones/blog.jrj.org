---
layout: post
title: Complexity
date: 2012-02-24 18:35
author: jrj
comments: true
tags: [Backup, JRJ Personal, security, Technology]
categories: [JRJ Personal, Technology]
---
A family member asked me if his technique of backing up his files to a thumb drive and regularly sending a copy to a safe deposit box was sufficient. My response was a reminder to me that I need to simplify my world. Nobody (including me) requires this level of complexity. What follows is my response, edited for posting.

<blockquote>
<p>The process you describe is sufficient, as long as you remember to do it consistently-- offsite backup is important. However, **I do prefer automated solutions.** Additionally, I would recommend encrypting the thumb drive if there is sensitive data in the folder you are backing up. You can either buy an encrypted thumb drive (I recommend <a href="http://www.amazon.com/gp/product/B002LASCU2/ref=as_li_ss_tl?ie=UTF8&amp;tag=privcast-20&amp;linkCode=as2&amp;camp=1789&amp;creative=390957&amp;creativeASIN=B002LASCU2" target="_blank">this one</a>) or just use <a href="http://truecrypt.org/" target="_blank">TrueCrypt</a> for free.</p>
<br />
<p>Personally, the way I back up is automated and has a lot of redundancy.</p>
<br />
<p>First of all, I use multiple machines (a desktop at home and at work, and a personal and work laptop means I'm starting with 4 machines.) This means that, to begin with, **I have at minimum 4 copies of every piece of data in 2 locations**. (I have things set up to sync automatically so if I make a change in one place it is reflected everywhere in seconds.)</p>
<br />
<p>For my PCs I have a **<a href="http://windows.microsoft.com/en-US/windows/products/windows-home-server" target="_blank">Windows Home Server </a>(WHS) that backs up an image of each PC on the network every night.** I have 7 days of daily backups, 2 months of weekly backups, 1 year of monthly backups, and indefinite yearly backups archived. I can restore any machine to its exact state at any point in time. This happens automatically, and I don't have to think about it. (WHS also centralizes ensuring virus definitions and security updates are up-to-date.) It's great.</p>
<br />
<p>**I've largely transitioned to Macs**, however. The process is similar for local backup, but is using different technology-- ultimately the backups end up on the WHS server.</p>
<br />
<p>The main data store is encrypted and a **differential upload is done on a weekly basis to the cloud**, encryption is happening on my end before the upload, and the key is never transmitted to the backup service, so they are incapable of decrypting the data. This is my primary offsite backup. (The services I recommend for this are <a href="http://carbonite.com" target="_blank">Carbonite.com</a> or <a href="http://crashplan.com" target="_blank">CrashPlan.com</a>)</p>
<br />
<p>Using a thumbdrive or optical discs is impractical for me because the **data in question is close to 7 terabytes** primarily due to my music, movie, and TV collections (All purchased, thank you very much) and longer-than-necessary historical backup archive. However, my most important data (images of important documents, etc.) is on 2 identical encrypted 64 gig thumb drives-- one is stored in the safe in my office, the other is in a bag that I keep locked in my car. (Physical security is not terribly important, since the data is encrypted.)</p></blockquote>
