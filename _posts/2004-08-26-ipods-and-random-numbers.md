---
layout: post
title: iPods and Random Numbers
date: 2004-08-26 11:10
author: jrj
comments: false
categories: [Uncategorized]
---
Paul (and the NY Times) calls into question the <a href="http://www.internet-nexus.com/2004_08_22_archive.htm#109352586508249634" target="_blank">quality of the "shuffle" functionality on iPods</a>:<br />*<blockquote>Just a thought, but maybe the shuffle software is poorly written. I've noticed this sort of thing on the iPod, but not on the Dell DJ, and I think it's a bit more nefarious than this article suggests: When you start shuffling music on the iPod, it seems to return to the same artist and even album again and again for some reason.</blockquote>* I'd be amazed if this was the case: every 1st year computer science student who took a class on data structures and elementary algorithm design knows about <a href="http://search.cpan.org/%7Eabigail/Shuffle-1.4/Shuffle.pm" target="_blank">Knuth's shuffling algorithm</a>, and pretty much every piece of software that has any kind of random order functionality (card games, music players, etc.) uses it. I'd be blown away if they don't.<br /><br />Obviously, the quality of the random number generator comes into question, but even a poor random seed wouldn't elicit the behavior you describe, since the full track list would be shuffled without regard to the meta data.<br /><br />In other words, if the behavior he describes is more than coincidence, it would almost have to be the result of intentional stacking, rather than a poorly implemented shuffle, as I don't think Apple's programming team is completely inept.
