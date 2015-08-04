---
layout: post
title: Local iOS Backup Locations
date: 2014-09-16 13:21
category: Technology
tags: [Apple, iOS, iTunes, JRJ Personal, Mac OS, Technology]
author: jrj
---
![Local iTunes Backups](/assets/postheads/itunesbackuploc.png "iTunes Backup Locations")

It's an interesting technological paradox: storage on devices (like phones and tablets) is growing at a geometric rate, but (for the first time in memory) storage on desktop and laptop PCs and Macs has been shrinking for years as they transition from hard drives to solid state disks. This becomes intensely frustrating if you want to maintain a local backup of all your devices.

Yes, I use iCloud backup as well, but I like having a local backup. Restoring is lightning fast (no [pun](http://en.wikipedia.org/wiki/Lightning_(connector)) intended) and reliable. Also, local backups include copies of media and apps so you don't have to download them separately. While I still strongly recommend iCloud backup to everyone (despite recent events, which would have been prevented by a strong password) that doesn't mean that local backups aren't useful.

The problem is that my iMac has a 128GB SSD, my iPad has 128GB of storage, and my iPhone has 64GB of storage. See the problem? Fortunately, I have a 3TB HD in my iMac as well for storage. The 128GB SSD only holds the OS and applications. However, the location to which iTunes backs up your devices is hard coded, and there's no way to change it. So, much like my solution for iTunes Media storage, I decided to set up a symbolic link-- a few simple steps and I'm up and running with local device backups:

1. Make sure the iTunes application on your Mac is closed

2. Move the folder called **~/Library/Application Support/MobileSync/Backup/ **to the new locations you want backups to live. In my case, this is a secondary internal hard drive, but it could just as easily be an external drive or a share on my NAS device.

3. Launch Terminal `Applications/Utilities/Terminalnd` type in the following command line:

```
ln -s /Volumes/JRJHDD/Backup/ ~/Library/Application\ Support/MobileSync/Backup
(replace "JRJHDD" with the name of your hard drive.)
```

Now, when you run iTunes and do a local backup of your iPhone or iPad it will go to the new location. You can accomplish the same on Windows using a tool called "[Junction](http://technet.microsoft.com/en-us/sysinternals/bb896768.aspx)."
