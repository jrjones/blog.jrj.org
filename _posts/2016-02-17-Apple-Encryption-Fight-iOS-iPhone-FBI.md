---
layout: post
title: "Apple Fights for Encryption"
date: 2016-02-17 20:45
category: Privacy
tags: [security, privacy, Apple, iOS, encryption, FBI, legal]
author: jrj
teaser: "Apple is playing chicken with the FBI over their right to build software and hardware that securely protects user data..."
image:
  homepage: "postheads/applefbi-plustitle.png"
  thumb: "postheads/applefbi-thumb.png"
  caption: "Apple is playing chicken with the FBI over encryption..."
header:
  image_fullwidth: "postheads/applefbi.png"
  title: ""
---

As you're probably already aware, [Apple is refusing a demand from the FBI (and corresponding court order) to enable the decryption of an iOS device][1] recovered from one of the San Bernadino shooters. I won't bother going over the basics of the story-- I'll assume you've already read some of the [mainstream accounts](http://www.theguardian.com/technology/2016/feb/17/inside-the-fbis-encryption-battle-with-apple?CMP=share_btn_tw) so I can focus on the some of the more esoteric (and, at least to me, more interesting) technical matters.

First, a couple assertions that I believe to be correct, but cannot prove:

* Apple and the FBI are both willing and able to see this through to the end, and it will ultimately be decided by the Supreme Court.
* The FBI is not seeking data on this phone, but rather the precedent for future use. 

While I can't prove either of those assertions, I believe that the information that's publicly available _is_ sufficient to conclusively determine that **it's not possible for Apple to decrypt this one phone without making such an attack possible against all similar phones.** Apple has said as much, but I believe that the published information about the iOS security architecture (and third party penetration testing to date) conclusively validates that claim.

## Well-documented security architecture 

Apple does not depend on "security through obscurity" to protect iOS devices. They are sufficiently confident in the security architecture that they have been quite open about it, [publishing detailed information about the protection techniques used][10]. The architecture has been widely vetted by the security community.

To summarize it, the data on a modern iOS device is AES encrypted with a unique key per file. That key is stored in the file's metadata[^1] encrypted with a `file system key`. The `file system key` is stored in the device's secure enclave,[^2] and the key can be securely deleted by the user interactively ("erase all content and settings") or in response to a security event such as a "remote wipe" or, if the user has so configured, after 10 consecutive incorrect login attempts. Without this `file system key`, the encrypted data is unrecoverable.[^3]

Since the `file system key` is securely deleted after 10 unsuccessful login attempts, it's impractical to attempt to brute-force even a simplistic 4-digit numeric passcode, since the cost of that incorrect 10th answer is unrecoverable data loss. However, **without that protection in place, brute-forcing a typical numeric passcode could be reliably accomplished in the time it takes for Dominos to deliver a pizza, so the FBI is demanding that Apple make it possible for them to defeat that mechanism so they can attack the weakest link in the security chain: the user's passcode.** It's worth noting that this technique would not be effective on a device with a strong password, and using a strong password is quite practical on a modern iOS device thanks to the TouchID sensor. I do it, and you should too.

So why can't the FBI simply "hack" the OS themselves? Because Apple's security features prevent a modified OS image from being installed. It's possible to update the operating system on an iOS device via USB without the passcode, but only if the OS image is digitally signed by Apple, a restriction which is enforced in hardware via Apple's Secure Boot chain. 

So, while it's possible to create a new OS that won't delete the encryption key after 10 successful login attempts, and it's possible to install such an OS on an iOS device without first logging in, Apple would need to digitally sign that OS image. This is what the FBI is demanding: they want Apple to create (and, more importantly, digitally sign) an OS image that be installed on the phone in question. With the erase-after-10-bad-login functionality disabled, the FBI could then simply brute-force the passcode (which is typically just a 4 or 6 digit number.)[^4] Apple is refusing to comply with this demand.

## What does this all mean?

There are a couple of interesting facets here. 

First of all, the phone in question is a 5c (which is, essentially an iPhone 5 in a colorful plastic case.) The device pre-dates the inclusion of the "secure enclave," which was introduced with the 5S an its A7 SoC. Based on my reading of Apple's security documentation, it's not clear to me that such a technique would be effective on a newer device, since the secure enclave is designed to maintain the integrity of Data Protection even if the main OS and kernel have been compromised. However, even though this specific technique is likely not applicable, it's highly probable that [some approach is possible with newer devices even though the technical demands would be different][20]. With the precedent set, the FBI could demand Apple create a new circumvention tool the next time around.

Second, the FBI is being very strategic here. They've chosen a case that's a.) highly incendiary/emotional, and b.) involves parties who are all dead. It's very difficult politically for Apple to fight this battle, but they're doing it anyway. It's risky, and I'm not convinced they can win it, but I'm impressed they are trying.

The question here is simple (and mirrors [a similar battle that the law enforcement community lost in the 90s][45].) **Is it legal for a company to produce a product which protects data so well that the company itself cannot recover it in response to a court order?** If courts find that the answer is "no" there will be far-reaching effects. For example, I use cloud-based backup because I was able to validate that the data is encrypted locally, and the encryption key is never sent to the cloud. I would not be able to use a cloud-based backup solution without such protection since if the company is compromised my data would be at risk. Ther are dozens (if not hundreds) of similar solutions that would no longer be feasible to implement.

Another way to frame the same question: [Should companies be legally obligated to integrate security circumvention technologies into their products?][50] 

For some reason, one simple fact seems to not be obvious to some people: U.S. Law only applies within our borders. If you prevent companies like Apple from implementing secure solutions (and/or force them to create circumvention functionality that bypasses their own security) you advantage international competitors. When faced with a choice between a known-compromised/backdoored device from an American company or a known-secure solution from a foreign competitor, which one do you think people will choose? Yes, you can mandate such solutions in the U.S., but we represent a small part of the global market. Even if we COULD compel companies outside our borders (hint: we can't) there's still the small problem that solutions, many of them open source, already did exist to encrypt data. The encryption cat is already out of the bag. (I'm just guessing, but I don't think terrorists would select the known backdoored solutions either-- they have a nasty habit of not cooperating with the preferences of law enforcement.)

**Personally, I'm on the side of Apple, the [ACLU][30], the [EFF][40], and others on this fight. I'm not confident they can win it, but I commend them for trying.**

[^1]: Files are encrypted with AES 256 (Cipher Block Chaining) using a unique key per file. The initialization vector is calculated with a block offset into the file, encrypted with a SHA-1 hash of the file key. The key is then wrapped (using AES key wrapping compliant with RFC 3394 and stored in the file's metadata.

[^2]: The "Secure Enclave" is a separate security coprocessor that is part of Apple's System on a Chip (SoC) A7 and above. It has its own secure boot, registers, and processing capability that is separate and explicitly segmented from the main CPU and memory, and it performs cryptographic and security operations on behalf of the user without making information available to the rest of the system. The concept of a secure enclave is not new-- it's included in the ARM specifications for TrustZone-- but Apple's implementation is subtly different and optimized for slightly different scenarios. The Secure Enclave has a feature called "Effacable Storage" designed to mitigate the difficulty of securely erasing flash storage so that keys can be securely erased at the request of the user or in response to a security event.

[^3]: I'm using "Unrecoverable" as a simplification. To be more accurate, recovery of the data is computationally infeasible without the decryption key, and guessing the decryption key through brute force is also infeasible. With a modern computer, it would take 3×10<sup>51</sup> years, even accounting for routine doubling of computational power via Moore's Law you are still flirting with the timeline by which our Sun will go super-Nova and we'll have larger concerns if we're still around. Quantum computing will make this problem more tractable, but cannot mount a practical attack against a 256 bit AES key in the foreseeable future. 

[^4]: The passcode is entangled with the device's UID, forcing brute force attacks to take place on the device being attacked (i.e. preventing offline attacks.) On newer devices (5S and above) time delays are enforced in hardware extending a theoretical brute force attack from ~30 minutes to multiple years unless Apple is forced to update the firmware in the Secure Enclave. 

[1]: http://www.apple.com/customer-letter/

[10]: https://www.apple.com/business/docs/iOS_Security_Guide.pdf

[20]: http://techcrunch.com/2016/02/17/why-apple-is-fighting-not-to-unlock-iphones-for-the-government/

[30]: https://www.aclu.org/news/aclu-comment-fbi-effort-force-apple-unlock-iphone

[40]: https://www.eff.org/deeplinks/2016/02/eff-support-apple-encryption-battle

[45]: https://en.m.wikipedia.org/wiki/Crypto_Wars

[50]: http://www.macworld.com/article/3034355/ios/why-the-fbis-request-to-apple-will-affect-civil-rights-for-a-generation.html