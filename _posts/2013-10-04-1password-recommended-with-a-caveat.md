---
layout: post
title: "1Password: Recommended with a Caveat"
date: 2013-10-04 06:54
author: jrj
tags: [1Password, Apple, iOS, Mac OS, passwords, cryptography, privacy, security, technology]
category: Security
teaser: "I strongly recommend 1Password, but don’t use one feature…"
image:
  frontpage: postheads/1passwordsharing.png
  thumb: postheads/1passwordsharing.png
header:
  image: postheads/1passwordsharing.png
  background-color: "#E2E2E2"
---
I'm a huge fan of [1Password](https://agilebits.com/onepassword), I use it daily and recommend it to everyone. When I found out that the [new version of 1Password for Mac OS X](https://agilebits.com/onepassword/mac)shipped today, I was very excited to try it out. (Though I'm an avid user of beta software, I would never use a beta for so critical a function.)

As a bit of a security geek, I review the core security tools I use for correctness from a design perspective (and implementation, where possible.) It's important to me that I fully understand how these tools work because I handle and share sensitive information in my line of work. Hence, **before I downloaded and installed version 4 of 1Password, I did a full review of their excellent architecture documentation.** I can give the new version a clean bill of health: indeed, it's even slightly more secure than the previous version. **I recommend 1Password version 4 to users looking for a password management solution, and recommend that existing users upgrade.** However, I do have one caveat that I must add to my recommendation: **Do not use the item sharing feature** to share sensitive information, including but not limited to passwords and credit cards. It should not be considered secure. To be clear, I'm not talking about the ability to have a secondary shared vault - this is fine, and I plan to set up a "household" vault to share with my wife this weekend for our shared accounts and data. It's the sharing of *individual items via iMessage or email* that I have issues with.

**Everything else about the product is rock solid**, the other new features are excellent. The design and user experience improvements are significant. I want to be clear that **I still recommend the product**, and definitely recommend that existing users upgrade. I'm simply saying that you** shouldn't use item sharing until AgileBits rearchitects that feature. **

AgileBits does a fantastic job of documenting their security architecture, and the mechanisms used to store and encrypt/decrypt your sensitive data. They get into the nitty gritty details of their key derivation routines, password brute force countermeasures, and other technical information necessary to assess the security of the product. I really appreciate this, as without this level of detail I would not be able to use the product. They have a [high-level security summary](http://learn.agilebits.com/1Password4/Security/security-overview.html), a [version 4 delta summary](http://learn.agilebits.com/1Password4/Security/1P4-security-changes.html), and a [more detailed document](http://learn.agilebits.com/1Password4/Security/keychain-design.html) available for your perusal.

Even though they provide reams of documentation, most of what you need to know they summarize in a few short sentences:

## The short answer

> The short answer is 1Password uses the best available encryption from well trusted and scrutinized cryptographic libraries. It is designed in accordance with the recommendations of the cryptographic research community. It is designed so that if anyone (including us) were to get a hold of your 1Password data there is no feasible way for them to decrypt your secrets without knowing your Master Password. We’ve even designed 1Password to make things extra difficult for systems that might try guessing your Master Password.

## The buzzword compliant answer

> 1Password 4’s **Cloud Keychain** format uses Encrypt-then-<abbr title="Message Authentication Code">MAC</abbr> for authenticated encryption with <abbr title="Advanced Encryption Standard">AES</abbr>-<abbr title="Cipher-block chaining">CBC</abbr>-256 for encryption and <abbr title="Hash-Based Message Authentication Code">HMAC</abbr>-<abbr title="256-bit Secure Hash Algorithm">SHA256</abbr> for Message Authentication. Key derivation uses <abbr title="Password Based Key Derivation Function Version 2">PBKDF2</abbr>-<abbr title="Hash-Based Message Authentication Code">HMAC</abbr>-<abbr title="512-bit Secure Hash Algorithm">SHA512</abbr>. On Mac and iOS 1Password uses [`SecRandomCopyBytes()`](http://developer.apple.com/library/ios/#documentation/Security/Reference/RandomizationReference/Reference/reference.html) from Apple’s security framework.

These summaries, and the more detailed documentation, are clear and well-written. They did a fantastic job of answering my questions... except after reading and re-reading all of the materials on their site, I still couldn't answer the question of how the new item sharing feature worked; or, more to the point, how it secured the information that was being shared. The omission was even  more striking because the documentation is otherwise so complete.

After a bit of searching around, I was able to find a (somewhat) old blog [post on the AgileBits blog that discussed the sharing feature from the iOS release](http://blog.agilebits.com/2013/05/14/understanding-sharing/) of version 4 released in May. This post makes it clear that the security of the item sharing feature is dependent on the security of the channel on which the data is being shared. Indeed, it's even described as "not human readable" but that anyone with a copy of 1Password could access the data being shared (for example, the password or credit card number) if they intercepted the message. This caused me to look at what's being shared, and it's pretty clear that **it's obfuscated, not encrypted... indeed, it's pretty weakly obfuscated.** (If I have time this weekend, I may update this post to include more information on the shared item format.) The sharing feature allows you to share over **two channels: iMessage, and e-mail. **

Now **iMessage is arguably a reasonably secure channel**, at least based on what we know about it. Apple doesn't disclose every last detail like AgileBits does, but what we know about iMessage indicates that it's reasonably secure. However, there's a big difference between "reasonably secure" and "secure." It's unlikely given what's known about the protocol that a malicious user could intercept iMessages, and equally unlikely that a man-in-the-middle attack would be viable. However, [there are strong indications that Apple themselves could gain access](http://blog.cryptographyengineering.com/2013/06/can-apple-read-your-imessages.html) to the data (meaning it would be potentially susceptible to a warrant or NSL) and the messages are also stored on your phone and in your backups, which may or may not be encrypted based on your settings. So one could argue that sending this information in an essentially unprotected format via iMessage is reasonable. I would disagree with that person, but I  wouldn't think they were insane. **My advice would be not to send anything you consider truly sensitive via iMessage.**

**However, there's absolutely no justification for enabling this feature over email.** This is inarguably a mistake, and one that the security folks at AgileBits should not have allowed to happen. The fact that 1Password even allows this **gives the user a false sense of security**, and makes people likely to assume it's secure. Indeed, even [fairly advanced users have indicated that they would be willing to use the feature] based on their inherent trust of AgileBits. The feature **should, at minimum, pop up a warning** indicating that this is not a good thing to do with sensitive information. Allowing users to send credit card numbers and passwords in an unprotected form like this is inappropriate, and I'm disappointed in AgileBits for enabling the feature.

Indeed, I would prefer that it literally be sent in the clear (which is an option-- but at least when doing that you know that you're doing it.) Users would KNOW it was being sent in the clear. Because of the generally opaque format, items shared in this fashion SEEM secure, and the user is understandably going to assume that to be the case in absence of a warning.

**AgileBits needs to rearchitect this feature.** Every 1Password user has an account with AgileBits... so why not generate an asynchronous key pair on the device and upload the public key to AgileBits' cloud? Then they could facilitate truly secure exchanges of items between users. Since the shared items can only be opened with 1Password anyway, lack of such an account isn't a blocker. Obviously, there could be something preventing them from implementing this in the way I'm describing - at minimum I'm oversimplifying the problem... but **if they can't actually fix it and architect it in a secure manner they need to remove the feature.** If they are unwilling to remove the feature, they need to at least pop up a warning indicating to the user that the feature should not be used with sensitive information (which is the only thing you're storing in 1Password) especially when the user chooses to send the data via email. I think they should remove it (or at least remove email sharing.) Too many people will use it to send passwords and credit card info via email otherwise.

**It's a fantastic product with one broken feature...** but a feature this poorly conceived reduces trust in the vendor's judgement and commitment to secure implementations.

**Again, I still strongly recommend the product as long as you avoid the item sharing feature.**

### Comments (archived)

<div style="background-color: silver; padding: 20px; border-top: solid 2px gray; border-bottom: solid 2px gray;">


<img src="http://1.gravatar.com/avatar/71778e2933aea1d0de7be59456b8633a?s=60&d=mm&r=g" align="left" style="margin-right: 15px;">

<h5>Jeffrey Goldberg</h5>
October 4, 2013 at 7:55 pm
<br clear="all"/>
(Disclosure: I work for AgileBits, the makers of 1Password)

Thank you!

I’m delighted that you appreciate the over all security design and the fact that we are open about it.

As for your caveat, I have to fully acknowledge that the item sharing feature as it stands now does not conform to an over all design principle of trying to make it easy for people to behave securely and hard to behave insecurely.

In other words, we don’t like to give people a way to shoot themselves in the foot, but the sharing feature may very well go against the grain of that approach.

a feature this poorly conceived reduces trust in the vendor’s judgement and commitment to secure implementations.

As you expect, I believe that our judgement and commitment remain sound, but I can’t fault you for questioning it. Indeed, it would be irresponsible not to. This is one of the reasons why we are open about our design. It is correct that you take this feature into account (along with everything else) in coming to your own conclusions.

I can’t make any promises about the future of the sharing, whether it will be removed, or accompanied with a strong warnings, or whether it is redesigned entirely. But your comments are well noted. The blog post about this does, in my view, a reasonable job of educating the users who read it all the way through, but that will be only a tiny portion of 1Password users.

Cheers, -j
<br />

<img src="http://1.gravatar.com/avatar/a771caefa1dcf4f219c4b4ae25f99f53?s=60&d=mm&r=g" align="left" style="margin-right: 15px;">

<h5>JRJ</h5>
October 5, 2013 at 7:38 pm
<br clear="all">
<blockquote>As you expect, I believe that our judgement and commitment remain sound, but I can’t fault you for questioning it. Indeed, it would be irresponsible not to. This is one of the reasons why we are open about our design. It is correct that you take this feature into account (along with everything else) in coming to your own conclusions.</blockquote>

To be clear, I also think that AgileBits judgement and architecture capabilities are generally excellent, and this has not significantly eroded my trust in the company and its products. Indeed, I continue to both use and recommend 1Password. There are alternatives, and I continue to choose 1P.

<blockquote>I can’t make any promises about the future of the sharing, whether it will be removed, or accompanied with a strong warnings, or whether it is redesigned entirely. But your comments are well noted. The blog post about this does, in my view, a reasonable job of educating the users who read it all the way through, but that will be only a tiny portion of 1Password users.</blockquote>

Exactly– the blog post will be read by 1% of your users, the other 99% will never know. A strong warning – even if it had a “never warn me about this again” button – would go a long way towards protecting users and making sure they understand what they are doing when they click “share.”

Thanks for listening – really appreciate it. Hope you’ll consider adding a warning.  :)
<br />
<img src="http://2.gravatar.com/avatar/55cb4e491df5406cdde36a94c3dd6853?s=60&d=mm&r=g" align="left" style="margin-right: 15px;">

<h5>Josh</h5>
December 17, 2013 at 12:18 pm
<br clear="all"/>
As one (also very satisfied) 1Password user who *has* read to the bottom, thank you for alerting me to the sharing weakness. I also appreciate your clarification that it’s just that one feature and the rest of the software remains strong.

</div>
