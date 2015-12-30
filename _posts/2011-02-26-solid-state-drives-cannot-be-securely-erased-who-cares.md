---
layout: post
title: Solid State Drives cannot be securely erased? Who cares?
date: 2011-02-26 00:00
author: jrj
comments: false
tags: [privacy, Security, security, SSD, Technology]
categories: [Security, Privacy]
---
With my recent purchase of a <a href="http://www.apple.com/macbookair/" target="_blank">MacBook Air</a> I've recently become **quite enamored with Solid State Drives** (<a href="http://en.wikipedia.org/wiki/Solid-state_drive" target="_blank">SSD</a>). The speed and silence is downright intoxicating, and prices are coming down fast (though still nowhere near parity with traditional hard drives.) One downside is that **SSDs can be very difficult to erase in a way that can't be easily recovered.** <a href="http://www.infoworld.com/t/solid-state-drives/flash-based-solid-state-drives-nearly-impossible-erase-263?page=0,0" target="_blank">A security resarch firm recently tested</a> several popular "secure erase" tools which perform multiple overwrites, and were in almost all cases able to recover the data. (Note that, in addition to SSD drives, **this applies to non-volitile flash memory like the thumb drive on your key chain**.)

My question is this: **Who cares?**

With tools like <a href="http://www.microsoft.com/windows/windows-7/features/bitlocker.aspx" target="_blank">BitLocker</a> in Windows 7, and the excellent open source <a href="http://www.truecrypt.org/" target="_blank">TrueCrypt</a>, there's no reason for these drives to include unencrypted data. Ever. Anyone who is concerned enough about the security of their data to want to perform a secure erase should be using tools like this to secure their data. **If you need to perform a secure erase you're doing it wrong. **

If the data is encrypted (and the algorithm and key used for encryption is cryptographically sound) then **you don't care if data is securely erased or not.** I'm perfectly comfortable donating old PCs to charity or selling them via services like<a href="http://www.gazelle.com/" target="_blank">Gazelle</a> without first erasing the drive because I know none of my hard drives contain any unencrypted data.
