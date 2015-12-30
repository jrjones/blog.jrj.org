---
layout: post
title: Optimizing Your Mac for SSD
date: 2012-06-25 20:47
author: jrj
comments: false
tags: [OS X, Apple, SSD, iTunes, howto]
category: Technology
header:
  image_fullwidth: jrj-itunes-directory.png
teaser: "Dealing with iTunes backups in a world of space-limited SSD drives..."
image: 
  thumb: postheads/itunesbackuploc.png
---
I use two primary machines for personal use: an **11" MacBook Air Core i5** (2011) and a** 27" iMac Core i7** (Late 2009). This is my second MacBook Air (my wife inherited the previous one) but when I first tried a MacBook Air, it was a revelation to me... not because it's a great laptop (though it is) but rather because despite the much slower processor and less RAM, it was *dramatically* faster for almost every purpose than my ostensibly more powerful iMac because of the speedy SSD. [I immediately upgraded my iMac to an SSD][1].

![iTunes folder screenshot](/images/postsupport/iTunesMedia.png)
{% include alert text="The iTunes folder, with the &quot;iTunes Media&quot; folder as a symbolic link to my NAS device." %}

However, all was not right in SSD-land. **I didn't want to sell a kidney to buy an array of solid state drives large enough to store my iTunes library**-- anything in the multi-terabyte range is just insanely expensive... so that meant my iTunes library was on an external FireWire drive. FireWire should have been fast enough for this purpose, but it's not-- **scrolling through a large iTunes library was slow and even caused instability** (iTunes would regularly crash, and if I didn't want to regularly see the spinning pinwheel of death while working on the iMac I had to quit iTunes.) It was horrible.

I couldn't store my entire iTunes library on the comparatively puny SSD. I could manually move content, but when I purchased something it would put it in the iTunes directory. I didn't want to micro-manage my media, and I knew there had to be a better way.

**What I'm doing now works perfectly**, and with many Macs now shipping with dual drives (one SSD, one HDD) I thought this might be useful to a lot of people.

The SSD on the iMac still has my operating system, apps, etc. It also has my iTunes folder in the standard location (in my case, `~/Music/iTunes/`)

However, the `~/Music/iTunes/iTunes Media/` directory **is now a symbolic link to my Network Attached Storage (NAS.)** Could just as easily be a firewire or USB drive, but my NAS is much bigger, and provides redundancy. (I did some quick ad-hoc testing, and gigabit ethernet was pretty much identical performance to firewire for my needs. If you have an internal drive or got a second mortgage on your house to buy a Thunderbolt drive then you'll get better performance there.)

Now the `iTunes Music Library.xml` file, album artwork, etc. (and hence all the navigation, scrolling, searching, etc.) is on the super-fast SSD, but all the data is stored on the network (and is accessible to other machines even with the iMac is turned off.) It works perfectly, and I couldn't be happier.

A couple quick caveats before I go into how to set this up for yourself:

  1. This is only practical for a desktop machine that is always connected to the external drive or NAS on which the data is stored, or in a MacBook Pro configured with a dual-drive SSD/HDD combination. If you're going to use a NAS, it really ought to be gigabit Ethernet, not WiFi.
  2. The "iTunes Media" directory will often be called "iTunes Music" if you're working with an old library. If this is the case, you may be better off creating a new iTunes library and copying your media into it. Having a fresh XML file may improve performance and reduce the memory footprint.

Here's how to migrate your iTunes content (but not the library and artwork cache) to an external drive:

  1. In the Finder, copy the folder from the SSD to the new location (in my case it was a NAS, but it could just as easily be an internal or external hard drive.)  Verify that the copy was successful-- you need to be 100% sure that your data isn't lost or corrupted.
  2. Go to the Terminal (usually in `/Applications/Utilities/`) and `cd` to the location of the *original* folder (on the SSD), and delete it. You can drag it to the trash or delete in the terminal by typing `sudo rm -rf foldername`
  3. While in the location of the *original* folder you just deleted (typically `~/Music/iTunes/`) make a link to the copy of the folder on the new location, by typing `ln -s /Volumes/MyNAS/media/iTunes/iTunes Media/`.  (Obviously, your location will be different.)

This will create the symbolic link... when you open iTunes, it will be using the same library and album art, but will be referencing the actual content in the new location, saving you precious gigabytes (or in my case terabytes) of precious SSD storage space.

You can do this with other directories as well (I'm looking at you, `~/Pictures/`!) but iTunes is sort of a special case since your performance will suffer so much with large libraries if you move them to an external drive without keeping the library and album art local.

Let me know if you have any issues with this.

**Update - July 2, 2012**

I did the same thing with my iPhoto library, though I recommend users tread lightly with this, since Apple semi-regularly tweaks the file format of the iPhoto library.

![iPhoto Library package in Finder](/images/postsupport/iPhotoLibrary.png)

{% include alert text="The iPhoto library is actually a special folder, or &quot;package.&quot; You can right-click on it to show package contents." %}

Though when you see it in the Finder it looks like a file, the iPhoto Library is actually a special folder, or "package." You can right-click on it and select "show package contents" to see the underlying files and folders, or you can navigate there in the command line.

The directories that are of interest to us are "Masters" and "iPod Photo Cache Directory" as these two directories are the overwhelming majority of the data, and the other folders (particularly the "Thumbnails" and "Previews" folders) are much smaller and contribute more to the performance of the iPhoto application.

I put both of these directories on the NAS with symobilic links, and it works great. However, only do this if you are backing the data up regularly, as if Apple decides to change the file format (they've done it before) then you can get some weird behavior.

[1]: http://blog.jrj.org/2011/02/26/solid-state-drives-cannot-be-securely-erased-who-cares/