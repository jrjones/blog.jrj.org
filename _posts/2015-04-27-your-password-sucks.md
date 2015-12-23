---
layout: post
title: Your Password Sucks
date: 2015-04-27 13:07
category: Security
tags: [1Password, hacking, LastPass, passwords, privacy, security, technology]
author: jrj
excerpt: "Your password sucks, but every character counts…"
image: "postheads/passwordsucks.png"
header:
  image: "postheads/passwordsucks.png"
  background-color: "#333333"
---
<!---
![Your Password Sucks](/assets/postheads/passwordsucks.png "Your Password Sucks")
-->

[Jeff Atwood has a great piece on Passwords](http://blog.codinghorror.com/your-password-is-too-damn-short/), with a heavy emphasis on length. He uses [Steve Gibson's Password Crack Checker](https://www.grc.com/haystack.htm) to estimate the amount of time needed to crack passwords of varying lengths, and the numbers will probably surprise you... and keep in mind, this is for a truly random password (like *"Uhs&amp;81Aj"*) - anything with variations of dictionary words, like *"M0nk3y!9"* would be MUCH faster. Indeed, that password would be cracked by most brute force cracking tools within a few seconds.

![Your Password is too Damn Short!](/assets/your-password-is-too-damn-short.jpg "Your password is too damn short!")

A random 8-character password using all character types takes over 2,100 years to crack in the "online attack scenario," which is guessing 1,000 attacks per second over a network. (And that's probably a bit optimistic - few network cracks could do that many requests per second. Figure it's probably 3-5X longer in most real-world online attacks.) Hence, it works great in this situation. **However, that's not how passwords are typically attacked.** A more realistic attack is that someone downloads a bunch of leaked password hashes from an online breach, and they can attack the password locally. On a typical computer, depending on the hashing technique used, this can be very fast, as in a hundred billion guesses per second fast. Using this technique, cracking our hypothetical 8-character password takes 18.62 hours. Obviously, this is unacceptable-- the password can be trivially cracked in under a day using a typical PC workstation.

The calculator also estimates for a scenario it calls a "massive cracking array." Most people think of this as "how fast can the NSA crack my password." However, keep in mind that virtually unlimited computing resources are available to anyone willing to pay for them via services like Amazon AWS or Microsoft's Azure, and instead of needing to build up a room with racks upon racks of servers (a huge capital expenditure) you can rent these resources by the hour. Simply spin up a few thousand machines, crack away, and then spin them down after an hour, at a much more approachable cost. Think a few dozen or hundreds of dollars.

Using this type of resource against our hypothetical 8-character password? 1.12 minutes. So you could spin up a bunch of AWS machines, and crack ~50 of them in an hour, then spin down.

Does this bother you? It should. However, increasing the length of passwords makes them only a tiny bit more difficult to remember, but geometrically more difficult to crack. Using the "Massive Cracking Array" statistic for a few different password lengths is instructive:

|                    | 8 char      | 10 char | 12 char   | 16 char                        | 24 char                                 |
|--------------------|-------------|---------|-----------|--------------------------------|-----------------------------------------|
| **MCA crack time** | 1.1 minutes | 1 week  | 174 years | 1.41 hundred million centuries | 9.38 hundred billion trillion centuries |


So going from 8 characters to 10 characters is the difference between a little over a minute and a week to crack.

Adding 2 more characters (for a total of 12) gets you to 174 years.

Willing to go to 16 characters? 1.41 hundred million centuries.

24 characters? We start flirting with the eventual heat-death of the universe.

Of course, this is with current computers... and they get faster every year, so these numbers will get smaller every year, in an exponential manner.

Bottom line? Download a password manager (I recommend [1Password](http://1password.com) to Apple-centric users, and [LastPass](http://lastpass.com) to Windows/Android-centric users.) Start generating different strong passwords for every site. And when you do, remember that suddenly the cost of increasing the length of your passwords is essentially free since you are neither remembering or typing them. Personally, I do 16-character passwords for most sites, 24 for high-security sites (like my work and banking passwords.) However, 12/16 would probably be perfectly reasonable for most users.
