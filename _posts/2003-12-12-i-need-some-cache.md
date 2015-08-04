---
layout: post
title: I need some cache
date: 2003-12-12 20:11
author: jrj
comments: true
categories: [Uncategorized]
---
One of the customers I was working with on my LA trip was hitting some performance bottlenecks, and we talked through implementing some caching functionality. This really got me thinking about the extent to which <a href="http://weblogs.asp.net/rhoward/posts/33865.aspx" target="_blank">Microsoft's caching strategy </a>(ala ASP.NET 1.1 and the upcoming Whidbey release) puts Macromedia's (ala ColdFusion MX 6.1 and the upcoming 7.0 release) to shame. Seriously... why doesn't Macromedia understand the value of caching with real controls in place for both design-time AND run-time? Why don't they get that a flexible caching solution is the only way that a web application server can scale in the real world?
<br />
<br />Caching-- both output caching and database caching-- is the lowest hanging fruit in terms of improving scalability and performance... wake up, Macromedia.
