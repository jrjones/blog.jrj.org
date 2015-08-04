---
layout: post
title: Zip subterfuge
date: 2003-09-08 06:14
author: jrj
comments: true
categories: [Uncategorized]
---
<a href="http://www.microsoft.com" target="_blank">Microsoft</a> caused me a pretty major headache this morning...
<br />
<br />I was re-arranging some computing resources on my home network, and I decided to ZIP up some files before sending them across a slow 100BaseT connection. (Well, slow when you're talking about my home file server... around 320 gigabytes of data.) So I zipped up a few shares, each between 5 and 20 gigabytes each. Microsoft's built-in Zip functionality took forever with this data, but after a while, it finished. The software was basically telling me "*OK! I'm done! Go ahead and delete the originals, secure in the knowledge that you have a nice safe, secure archive.*"
<br />
<br />Bastards.
<br />
<br />I moved the archives over to another system, and re-formatted the original drive. Then I tried to unzip them to their new home... and I got an error saying that the zip file was corrupt... I was horrified. All that data!  I have week-old backups of everything, but I would HATE to have to deal with a restoration! So what went wrong?
<br />
<br />Well, it turns out that the **ZIP format only supports archive file sizes up to 4 gig**... something <a href="http://www.winzip.com" target="_blank">WinZip</a>, <a href="http://www.aladdinsys.com" target="_blank">Stuffit</a>, and other decent Zip compression implementations will tell you if you try to create a file that exceeds that limit... but not Microsoft's implementation.
<br />
<br /><a href="http://support.microsoft.com/default.aspx?scid=kb;en-us;301325" target="_blank"><img src="http://www.jrj.org/nozip.gif" border="0" /></a>
<br />
<br />No... theirs just pretends like it finished successfully. It basically flushes your data down the toilet without telling you anything is wrong. <a href="http://support.microsoft.com/default.aspx?scid=kb;en-us;301325" target="_blank">Here's the admission</a> straight from the horse's mouth. (Or, given my current mood, straight from the horse's ass!)
<br />
<br />Bastards.
<br />
<br />All wasn't lost though... I downloaded <a href="http://www.repairfile.com" target="_blank">Advanced Zip Repair</a>, and it got about 99% of my data back without a hitch. Saved me from spending 6 or 7 hours restoring a third of a terabyte from backup.
<br />
<br />However, that doesn't get Microsoft off my shitlist... a bug like that is unforgivable.
<br />
