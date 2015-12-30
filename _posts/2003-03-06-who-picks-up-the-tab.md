---
layout: post
title: Who picks up the tab?
date: 2003-03-06 15:36
author: jrj
comments: false
categories: [Uncategorized]
---
An <a href="http://ask.slashdot.org/askslashdot/03/03/06/204235.shtml?tid=95" target="_blank">interesting discussion</a> going on over at Slashdot regarding a new issue in ISP billing. The question is this:
<br /><blockquote>
<br />"I am involved with network management in the hosting department of a fairly large ISP. Constantly we have customers who dispute inbound bandwidth spikes and demand service credits on their burstable connections. Events such as the Slammer Virus literally have everyone knocking on their salesperson's door at the end of the billing cycle. My position is that the internet is a public space, and by placing themselves in that space, one has to realize the consequences (and the implications of burstable billing). I'd like Slashdot's perspective on this. Should ISP's ultimately eat the costs of malicious behavior? Is the customer ultimately responsible for the bandwidth they've generated, regardless if it's desired or not? Is this a new frontier for insurance companies?"
<br /></blockquote>
<br />
<br />This is an interesting question, indeed, it is one that my company <a href="http://www.criticaldomain.net" target="_blank">Critical Domain</a> had to wrestle with not long ago. The real issue here is this: the ISP must make it extremely clear that the customer is responsible for maintaining a secure network, and that they are responsible for any incursions into their system. Otherwise, the ISP is, by default, taking responsibility. In the incident that occurred with Critical Domain, our ISP did not have such a clause, and they did eat the bandwidth cost... however, we offered to pay some of the fees anyway because we felt responsible for not being up to date on some patches. (Oh, the shame!) The ISP didn't take us up on our offer to pay some of the fees.
<br />
<br />This is going to be more and more of an issue as the security environment becomes more and more complex, and as exploits become more common and increase in their sophistication. Where do you draw the line? I think a good place to start is that a customer of an ISP should be contractually bound to take certain obvious precautions:
<br /><ul>
<br /> <li>Deployment of a real firewall</li>
<br /> <li>Stay no more then 1 week behind current patches to OS and network applications</li>
<br /> <li>Deployment of a server-class anti-virus product</li>
<br /></ul>
<br />
<br />You could extend this to include the deployment of intrusion detection systems, but I think that goes a bit beyond what can be expected of a "baseline" requirement,
<br />
<br />If the customer of said ISP meets these requirements, I think that the ISP shares some of the responsibility... but if even one of these assertions proves false I think that one could easily make a case that the customer is grossly negligent, and therefor fully responsible for any bandwidth costs incurred by an attack. Everyone knows that it is impossible to have a truly secure network that is attached to the Internet... however, I don't think that this is a problem from the standpoint of legal responsibility. Courts for years have based these kinds of decisions on whether or not a party took "reasonable steps" to avoid an incident, and networking is no different. I do think that the Internet services community (both ISPs and their customers) need to come together and agree on what constitutes taking "reasonable steps" to secure a network. Indeed, this would create benefits far beyond just making better contracts-- it would dramatically reduce the impact of new malicious code.
