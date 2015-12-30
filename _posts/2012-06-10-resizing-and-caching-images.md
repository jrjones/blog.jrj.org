---
layout: post
title: Resizing and Caching Images
date: 2012-06-10 21:51
author: jrj
tags: [ColdFusion, development, JRJ Personal, jrj-image-server, open source, GitHub, metablog]
categories: [Technology, JRJ Personal]

header:
  image_fullwidth: postheads/github.jpg
  
teaser: "A new open source project for auto-scaling images..."
image:
  thumb: postsupport/github.jpg
---
The previous version of the jrjBlog was based on the excellent open-source [Mango ColdFusion blog engine][1]. I liked it primarily because it was easy to tweak the code and implement fun new features on the site, but in the end I finally gave up and migrated to [WordPress][2] because of the availability of so many wonderful plug-ins.

**One thing I really miss is the image caching server that I had written for the old jrjBlog.** It allowed me to store a single high-resolution version of each image, and dynamically request and cache an infinite number of resized versions. I'm now in the process of bringing this feature back to the site (primarily so I can serve high-resolution images to high density screens like Apple's retina displays, and lower-resolution images to mobile devices.) Since I was separating the image server from dependencies on the old jrjBlog site, **I figured I'd make it open source**.

I've [published the source code to GitHub], including all necessary source files to get up and running. I even included a couple of images to make it easier to test and confirm that everything is set up correctly. It's licensed under the [MIT license][4].

## [View on GitHub][5]

The system requires [ColdFusion][6], and has been tested with versions 8, 9, and 10. It works fine on Unix, Linux, Mac, or Windows servers. Should work fine with any of the popular CF hosting providers. I haven't tested it on Railo or anything, if anyone wants to tweak it to work on an open source CFML engine I'm cool with it, but I'm too lazy to do it myself.

Enjoy, and let me know if you have any issues.

[1]: http://www.mangoblog.org
[2]: http://wordpress.org
[3]: https://github.com/jrjones/jrj-image-server/
[4]: http://en.wikipedia.org/wiki/MIT_License
[5]: https://github.com/jrjones/jrj-image-server
[6]: http://www.adobe.com/products/coldfusion-family.html