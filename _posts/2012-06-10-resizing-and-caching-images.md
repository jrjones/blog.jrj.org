---
layout: post
title: Resizing and Caching Images
date: 2012-06-10 21:51
author: jrj
comments: true
tags: [ColdFusion, Development, JRJ Personal, jrj-image-server, Open Source, Technology]
categories: [Technology, JRJ Personal]
---
The previous version of the jrjBlog was based on the excellent open-source <a href="http://www.mangoblog.org" target="_blank">Mango ColdFusion blog engine</a>. I liked it primarily because it was easy to tweak the code and implement fun new features on the site, but in the end I finally gave up and migrated to <a href="http://wordpress.org" target="_blank">WordPress</a> because of the availability of so many wonderful plug-ins.

**One thing I really miss is the image caching server that I had written for the old jrjBlog**-- it allowed me to store a single high-resolution version of each image, and dynamically request and cache an infinite number of resized versions. I'm now in the process of bringing this feature back to the site (primarily so I can serve high-resolution images to high density screens like Apple's retina displays, and lower-resolution images to mobile devices.) Since I was separating the image server from dependencies on the old jrjBlog site, **I figured I'd make it open source**.

I've <a href="https://github.com/jrjones/jrj-image-server/" target="_blank">published the source code to GitHub</a>, including all necessary source files to get up and running. I even included a couple of images to make it easier to test and confirm that everything is set up correctly. It's licensed under the <a href="http://en.wikipedia.org/wiki/MIT_License" target="_blank">MIT license</a>.

[button link="https://github.com/jrjones/jrj-image-server" type="big" newwindow="yes"] View on GitHub[/button]

<br /> The system requires <a href="http://www.adobe.com/products/coldfusion-family.html" target="_blank">ColdFusion</a>, and has been tested with versions 8,9, and 10. It works fine on Unix, Linux, Mac, or Windows servers. Should work fine with any of the popular CF hosting providers. I haven't tested it on Railo or anything, if anyone wants to tweak it to work on an open source CFML engine I'm cool with it, but I'm too lazy to do it myself.

Enjoy, and let me know if you have any issues.
