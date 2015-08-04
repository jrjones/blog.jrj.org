---
layout: post
title: Sisyphus and Systems Administration
date: 2003-09-04 21:11
author: jrj
comments: true
categories: [Uncategorized]
---
I was talking the other day to Rachel about the fact that one of the most effective and horrific torture techniques known to man was to force someone to dig enormous holes, and then fill them up with the debris created by digging the next hole... on and on, you keep creating new holes, filling them in with dirt from the next hole. The reason this is so cruel is because people hate to do useless work. I used the word "Sisyphean," an aligorical reference to the <a href="http://www.mythweb.com/encyc/entries/sisyphus.html" target="_blank">Corinthian king</a> of Greek mythology, condemned to forever roll a huge stone up a hill in Hades only to have it roll down again upon nearing the top.
<br />
<br />Why do I bring this up? Well, because that's how I feel about patch management lately. Critical Domain's policy is to make sure all our production servers are up to date twice a week, which includes the operating systems, any network applications (i.e. SQL, Exchange, etc.) and security tools (server antivirus, intrusion detection, etc.) It is a sad state of affairs when you have to do this twice a week-- it is very time consuming, and, quite literally, the rock rolls right back down the hill when you're done, since new patches are released literally daily. If we wanted to truly stay on top of this we would need to have a full time employee who did nothing but manage patches. Insane.
<br />
<br />There are some things that can be done to make patch management more... well... manageable. However, they don't help much. It is nice that Microsoft is making patch management a huge component of their <a href="http://www.microsoft.com/technet/treeview/default.asp?url=/technet/security/tips/Overview.asp" target="_blank">security best practices</a>, which they are doing a reasonable job of developing and supporting, but it isn't enough. This stuff needs to be more automatic.
<br />
<br />Today, Microsoft <a href="http://www.microsoft.com/security/security_bulletins/ms03-007.asp" target="_blank">released a patch</a> for the worst kind of vulnerability: one not first found by researchers, but by crackers. The vast majority of vulnerabilities are found by security professionals and "white-hat" hackers, who inform the company and give them time to develop a patch before an announcement is made... however, this one was found by the hackers first, and has been exploited already, even though the patch was released only today. (Obviously, Microsoft is taking this one seriously: they normally only release patches on Thursdays.) For example, the vulnerability exploited by the recent SQL "<a href="http://www.sarc.com/avcenter/venc/data/w32.sqlexp.worm.html" target="_blank">Slammer</a>" worm was fixed by a patch that pre-dated the worm by several months. Scary stuff.
<br />
<br />Patch your servers early and often... and hope that someone will make it easier some day.
<br />
