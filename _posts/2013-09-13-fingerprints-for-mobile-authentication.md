---
layout: post
title: Fingerprints for Mobile Authentication
date: 2013-09-13 03:15
author: jrj
tags: [authentication, biometric, fingerprint, iPhone, privacy, security, technology]
Category: Security
---

A couple days ago, Apple formally announced what the rumor sites had been talking about for months: **the new top-of-the-line iPhone has a fingerprint reader.** The basics are described in this brief promo video by the boys in Cupertino, embedded below.

Since then, I've seen literally dozens of silly, hyperbolic, and downright misleading articles about it, and I wanted to address a couple of assertions that I've seen around the web. The writers of most of these articles either know nothing about security,or are more interested in page views than accuracy. (My guess is "both.")

<iframe width="100%" height="400" src="https://www.youtube.com/embed/TJkmc8-eyvE" frameborder="0" allowfullscreen></iframe>

# Assertion 1: Fingerprints are insecure for authentication
Well, this one at least has some basis in fact. However, it's completely off the mark when considering mobile phones. Yes, a strong password (say, for example, a 16+ character pseudorandom string consisting of all character types) is significantly more secure than a fingerprint authentication. However, **that's not what you're using on your phone.**

According to Apple,** roughly half of iPhone users have no password at all on their phone.** This is disturbing - think about how much personal data is on that device, and how susceptible it is to loss and/or theft. The mind boggles that someone would not have a password set up on a smartphone.

**Effectively all of the other half uses a 4-character numeric password.** Trust me, a fingerprint is profoundly more robust than a numeric password. (I bet yours is one of a dozen or so common passwords. One study I read indicated that over half of the subset of phones that do have a password use one of the top 15 sequential or grid-pattern numeric pins, or a spouse/child's birthday.)

**While a fingerprint reader is less secure than a strong password, it's dramatically more secure than a 4-character numeric pin. **

The ideal, and what I recommend for your most secure data, is multi-factor authentication. Essentially, there are three possible factors:

<!---
[caption id="attachment_1245" align="alignright" width="300"]<a href="http://jrjblog.constellationofideas.com/wp-content/uploads/sites/9/2013/09/Slide2.jpg"><img class="size-medium wp-image-1245" alt="Something you know, something you have, and something you are = multi factor " src="http://jrjblog.constellationofideas.com/wp-content/uploads/sites/9/2013/09/Slide2-300x225.jpg" width="300" height="225" /></a> Something you know, something you have, and something you are = multi factor[/caption]
-->

- Something you know (like a password)
- Something you have (like a smart card or cellphone)
- Something you are (like a biometric)

By combining two or more of these factors, you can develop a very secure authentication system. For example, my most sensitive information at work (as well as remote access to our network) is gated by something I know (a password) _and_ something I have (an authentication token that generates a new code every 30 seconds.) I use a similar protocol for protecting the private keys associated with my PGP and personal certificates. This is how you treat your most sensitive data.

However, my normal data - email, files, etc. -- are simply stored on an encrypted disk protected by my password. Now it's a good password, and it changes every 3 months. However, I don't use multi factor auth for my day-to-day computer use. (I do for some services, for example, LastPass and Gmail, since both are fulcrum points for authentication to every online service I use.)

My phone stores a subset of my data. It has 3 weeks of email (unlike my computer, which has an email archive going back to 1991.) It has only a few current documents I'm working on. And, of course, a copy of my photo and music libraries. Nothing too sensitive. The most sensitive thing on there is probably my notes, which I do occasionally encrypt sensitive strings in. Getting access to my phone is bad, but it's not as bad as getting access to my computer.

**Everything comes down to a balance between security and convenience,** which are almost always at odds with one another. However, for once - and this is literally the first time I can remember this happening - we're getting something for free. **A fingerprint is not only more secure than a 4-digit passcode, but it's more convenient, too!** Maybe it will even convince some of those folks who don't have a passcode of any kind on their phones.

Note that the most security conscious of us will still have strong passwords on their phones. However, that's probably 2% of the population. If it's a good, strong password, it's more secure than a fingerprint reader, but at a very high cost in convenience. My preference is to simply not store anything highly sensitive on my phone unless encrypted and protected by its own password-- by not storing anything highly sensitive there, a fingerprint will be more than sufficient.

How secure will the sensor be? Well, based on the state of the technology developed by the company they acquired last year, pretty good but no better than others. The enrollment process indicates they are optimizing (correctly, I think) for reliability over security. We don't know until the thing comes out and gets tested (and it WILL be tested) but I'd estimate that **it will be better than the proverbial 4-character PIN, but possible to fool with some effort**-- how much effort remains to be seen, but if we assume the tech that was developed by AuthenTec has not improved at all in the last year, it will not be trivial.

# Assertion 2: A thief will cut off your thumb to get into your phone!
Two problems with this ridiculous fear mongering by so-called "security experts."

First, it's a capacitive sensor. **If a thief cuts off your thumb, or kills you, it won't work.** It needs living tissue. (I'd be interested in the QA protocol for validating this.)

Second, it seems to me that, by the time the thief had you incapacitated to the point where you couldn't prevent them from cutting off your thumb, and had the hacksaw to your hand, **they could probably convince you to simply give them the 4-character numeric password and have to deal with less blood.**

[![Security Comic](http://imgs.xkcd.com/comics/security.png)](http://xkcd.com/538/)

# Assertion 3: Oh noes! I don't want my fingerprint uploaded to Apple's servers and handed over the NSAs!
First of all, Apple has stated clearly (and without wiggle words) that your biometric data is stored in the secure store on the A7 S0C (which is [a VERY high bar](http://infocenter.arm.com/help/index.jsp?topic=/com.arm.doc.ddi0333h/Chdfjdgi.html) for security) and **never uploaded to or backed up to Apple's servers.** It stays only on your device, and is a stored in a very secure manner.

<!---
[caption id="attachment_1247" align="alignnone" width="1024"]<a href="http://jrjblog.constellationofideas.com/wp-content/uploads/sites/9/2013/09/Photo-Sep-22-1-45-36-PM-e1381172437751.jpg"><img class="size-large wp-image-1247" alt="The NSA's Utah Data Center outside Lehi, UT" src="http://jrjblog.constellationofideas.com/wp-content/uploads/sites/9/2013/09/Photo-Sep-22-1-45-36-PM-e1381172437751-1024x372.jpg" width="1024" height="372" /></a> The NSA's Utah Data Center outside Lehi, UT[/caption]
-->

Of course, we can't actually trust that statement. Even if you assume Apple is telling the truth (not a *completely* unreasonable assumption) then there's nothing to say that the U.S. government won't compel them to change that, and then force them under penalty of jail for their executives not to tell anyone that it changed. So **we can't trust that it will never be uploaded.**

However, **your fingerprints are, by definition, not a secret.** That's the difference between a password (a secret) and a biometric (which is a statistically unique measurement of biological properties.) Those properties are observable, and discoverable without your consent.

If the NSA wants your fingerprints, believe me: they have them. If you're worried about them getting biometric information then you would have to take some pretty unreasonable steps to prevent it:

1. Don't move to California, or any other state that has a fingerprint as part of driver's license.</li>
2. Wear gloves 24/7 when outside your home, since you wouldn't want to leave your precious fingerprints on a doorknob or beerstein.</li>
3. Don't get a passport, since it requires a biometric.</li>
4. Always wear sunglesses, even at night, since you can get a retina scan from a high resolution photograph.</li>
5. And steer clear of every camera that's in public, since gate detection is much more reliable a biometric than fingerprints.</li>

I could go on, but** the notion that your fingerprints should be guarded as a secret is a false premise** to anyone with any kind of security background.

# The bottom line: This is a good first step.

Authentication is a hard problem, and the constant friction between security and convenience presents a difficult trade-off. I think this is a reasonable optimization. **I hope that other phone vendors implement similar solutions. Indeed, I hope they innovate and develop something better. **
