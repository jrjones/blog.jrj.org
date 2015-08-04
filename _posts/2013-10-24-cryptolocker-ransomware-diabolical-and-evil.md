---
layout: post
title: "Cryptolocker Ransomware: Diabolical and Evil"
date: 2013-10-24 03:43
author: jrj
tags: [cryptolocker, malware, ransomware, Security, security]
category: Security
---

![Cryptolocker](/assets/postheads/Cryptolocker.png "Cryptolocker")

The idea of "ransomware" is nothing new, it's been done before. However, I don't think there's a past example of ransomware that has demonstrated this level of technical proficiency. The latest threat, known as **"Cryptolocker," is positively diabolical**.

Not only does it securely encrypt and hold your personal data ransom, the worst part is that the implementation is so good (and modern cryptography and bitcoin technologies sufficiently advanced) that** it's unlikely we'll be able to shut this thing down any time soon. **My real concern is that Cryptolocker is going to generate a lot of ill-gotten gains, and that cash can be funneled into improving it and widening its scope. I suspect this is only the beginning.

<!---
[caption id="attachment_1287" align="alignright" width="300"]<a href="http://blog.jrj.org/2013/10/24/cryptolocker-ransomware-diabolical-and-evil/th-paypage-4801/" rel="attachment wp-att-1287"><img class="size-medium wp-image-1287 " alt="Cryptolocker's digital ransom note" src="http://jrjblog.constellationofideas.com/wp-content/uploads/sites/9/2013/10/th-paypage-4801-300x235.png" width="300" height="235" /></a> Cryptolocker's digital ransom note[/caption]
-->

Cryptolocker infects your machine, typically via an email phishing attack, and then **encrypts your personal data: documents, videos, photos, everything.** Not just your primary copy, but any** live attached backups**. (an offline backup would be safe.) The malware **holds the decryption key ransom, currently for $300.** Unless you give them the cash within 72 hours, they delete the key. As mentioned before, the implementation is perfectly deployed for its malicious end: the decryption key is not present on your computer by the time you get the warning. If you don't pay them before the deadline the decryption key is deleted from their servers, and **you will never get your data back.** And given the sophistication of the malware's implementation and the anonymity inherent to bitcoin transactions, it seems likely that the attackers may never get caught.

I heard about Cryptolocker via [Steve Gibson](http://twitter.com/sg_grc), and he has a great discussion about it in his most recent [SecurityNow podcast](http://twit.tv/sn). (The [video below is set up to start right at the point where they are talking about Cryptolocker](http://youtu.be/ipaHgMedao4?t=39m6s).) His discussion goes into more depth, and is worth a listen if you're interested.

<!--- http://youtu.be/ipaHgMedao4?t=39m6s -->

We can't effectively go after the perpetrators by tracking the payments because they're accepting their ransom payments via bitcoin - totally anonymous. Though they have some clever countermeasures to prevent their domain names from being taken down, it's still possible... but it does no good, and only hurts the threatened users by deleting the only copy of the decryption key.

**I have a feeling this one is going to be with us for a while.** Currently, it's **Windows only**, but I expect that to change. To repeat, this is a financially motivated attack, which means they will continue to widen the circle, and could use the proceeds from the low-hanging-fruit to fund acquisition of zero-day exploits to go after fully patched machines without user error. I definitely expect them to go after the Mac, as those users are even less security conscious, and statistically have higher disposable incomes to target.

Standard advice applies - if you follow this you will be safe not only from this threat, but a lot of others as well:

- Don't open email attachments you're not specifically expecting. I don't care what the filetype is, or who it came from. Don't do it.</li>
- Don't click on links in email (type the URL yourself if you're confident it's a site you intend to visit.)</li>
- Keep your software (including operating system and apps) up-to-date, turn on auto-update where available.</li>
- Run anti-malware software, and keep its definitions up-to-date. (I'm still willing to concede that this is probably unnecessary on Mac OS today, but that's not going to be true forever.)</li>
- 3-2-1 Backups: 3 copies, in at least two different formats, one of which is off-site. (Off-site is accomplished either with a pair of drives that's rotated and stored off-site, or a cloud-based solution like Carbonite or CrashPlan.)</li>

However, if they start buying up zero-day vulnerabilities then only that last one is going to keep you safe.

**If you're infected and you don't have an offsite/offline backup... honestly, I have to begrudgingly recommend you pay up.** Get law enforcement involved, but you don't want them to take down the server that has your keys because if they do you'll never get your data back. The only real cure is prevention: Back up NOW... and again, it has to be an offline backup.

Stay safe out there!

> **Update:** [This site has incredibly detailed information](http://www.bleepingcomputer.com/virus-removal/cryptolocker-ransomware-information), including removal and threat avoidance. Update 2: Some good [advice and coverage from Krebs](http://krebsonsecurity.com/2013/11/how-to-avoid-cryptolocker-ransomware/). To be clear, while "removal" is trivial, it doesn't get your data back. For that, you still have to pay. Also, a friend of mine was infected, and paid. Her data is currently decrypting and it's looking like a full recovery is likely... but the bad news is that she gave $300 to bad guys who will use it to steal from others.

> **Update:** Gibson has posted a victim's story of getting their data back. Worth a read.
<blockquote class="twitter-tweet" lang="en"><p lang="en" dir="ltr">CRYPTOLOCKER (Take Two): Here&#39;s a PDF of Rob&#39;s experience with CryptoLocker that MY site is hosting: <a href="http://t.co/LZQ5DvVLy8">http://t.co/LZQ5DvVLy8</a></p>&mdash; Steve Gibson (@SGgrc) <a href="https://twitter.com/SGgrc/status/394938865107992576">October 28, 2013</a></blockquote> <script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>