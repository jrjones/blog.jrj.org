---
layout: post
title: Keep Your Systems and Accounts Secure
date: 2012-08-09 21:16
author: jrj
tags: [apple, hacking, privacy, security, amazon, backup, 2fa, passwords, LastPass, 1Password]
category: Security
teaser: "Matt Honen's story makes us all think a little more about security..."
image: 
  thumb: stock/cloudsec.jpg
---
[This article][1] is very scary-- it describes [Mat Honen's incredibly nasty experience of being hacked][1], and the process the attackers went through to destroy his digital life. Some positive developments since this story was published: it is very likely he will be able to recover the data on the laptop, including the photos. He was smart enough to remove power from the machine before the erasure was complete, so overwrite never took place, and Apple is cooperating with a data recovery service to get the data back. Also, [both Amazon and Apple have changed their policies in response][2] to this story.

The really scary thing: the reason the hacker cited for going after this guy was that he had a three-character twitter handle. You know, like [@jrj](https://www.twitter.com/jrj).

My wife asked me today if we were safe from this kind of attack. Unfortunately, there's no way to protect yourself from poor policies on the part of vendors, which was the vulnerability exploited in this instance. Now granted, in my case we would not lose any data-- everything is [backed up in multiple places and formats], and none of our personal computers are configured to enable remote erasure anyway... but if someone really wanted to take over our accounts bad enough they would likely be successful.

While none of our personal laptops or desktop machines are configured for remote deletions, all of our phones and tablets are, and I recommend others do the same-- they aren't storing any data that isn't elsewhere, and they are easy to lose/steal. Accidental erasure of a phone or tablet is a mild inconvenience. I would never recommend a computer be set up this way except in very special circumstances. (Interestingly, my work laptop is one of these special circumstances.) It's an interesting trade-off that protecting data against disclosure attacks makes it more vulnerable to denial-of-service (in this case deletion) attacks.

I have my primary personal email account (which is hosted with Google Apps) [set up for two-factor authentication][4], which is an enormous pain in the ass (which is why most people aren't set up this way.)

So what are my recommendations for people who want to make an attack like this more difficult? Unfortunately, the short answer is "make things more secure by making them less convenient."

 - Use a password manager-- I have reviewed [LastPass][5] and [1Password][6], and consider both trustworthy because the data is encrypted on the client side, so these companies don't even have your information if configured properly.
 - Use a different strong password for every site, and change them every 3-6 months depending on sensitivity. (A password manager is the only way to make this practical, which is why I recommend it.) If you password is more human readable or memorable than K83k$gPhw#k3j*02 then you're doing it wrong. Don't use a word with a few substituted characters like $erindip1ty. That can be brute forced in about 12 minutes. LastPass and 1Password both have great password generation features-- use them.
 - From now on when asked for "security questions" enter a long string of random data. For example, my mother's maiden name is often something like "8kj38d*i#l10kQo)ty" or similar. All real answers to security questions can be trivially researched, and since you have effective means of tracking passwords you'll never need to recover your account anyway.
 - Don't daisy-chain your critical accounts. In other words, don't have iCloud email password recovery emails to your main gmail account and vice versa. Have accounts just for this purpose ([hushmail][7] is great) or intentionally use accounts that don't exist.
 - If your email service has a two-factor authentication option, make use of it. It's unfortunate that email is the lynchpin of every other account, but that's how everything works today. Protect your email account above all else.
 - Lay low. Keep a low profile. Don't taunt hackers. Don't draw a giant target on yourself or in any way make yourself a juicy target.

All this will help make it more difficult, but not impossible, for someone to similarly "p0wn" your accounts and your data. There's no silver bullet.

[1]: http://www.wired.com/gadgetlab/2012/08/apple-amazon-mat-honan-hacking/
[2]: http://article.wn.com/view/2012/08/08/Apple_And_Amazon_Fix_The_Security_Holes_That_Caused_Wired_Ed/
[3]: http://blog.jrj.org/2012/02/24/backup-home-server-complexity/
[4]: http://www.mattcutts.com/blog/google-two-step-authentication/
[5]: https://lastpass.com
[6]: https://agilebits.com/onepassword
[7]: https://hushmail.com