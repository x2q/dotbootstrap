---
layout: post
published: true
title: Linux Kernel mailing list member
permalink: /linux-kernel-mailing-list-member/
wordpress_id: 1
categories:
- News
- Linux
- login manager
- Greg Davis
---


Today I subscribed to the <a href="https://www.kernel.org/">Linux kernel</a> <a href="http://vger.kernel.org">mailing list</a>

Here is my first mail received as Linux Kernel mailing list member
<blockquote>
This is probably an isolated incident, but I am having kernel hangs using 2.6.10 thru 2.6.11-rc3.  I have tried all different patchsets (mm, ck, cko), and all produce the same behavior.  2.6.8.1 does not produce the behavior.
Basically, after a few minutes, the kernel hangs, and interrupts are apparently not working as the keyboard leds don't respond anymore.  I recently swapped out a cdrom for a dvdrom drive, and was able to use it fine for a while with ck4 patched to 2.6.10.  Then I got gutsy and tried the mm patch for 2.6.10, to start using reiser4.  That was when the kernel started doing this hanging.  One surefire way to trigger a hang is to start a dvd with mplayer:  the dvd reads the first few frames of any dvd, then hang; however, hangs happen randomly otherwise.  I am running KDM as a login
manager, and X obviously when this happens, but without DRI. 
I also have tried going back to vanilla kernel, reformatting my drive to reiserfs3, and an otherwise previous state, but the kernel still hangs.  I even unplugged lots of stuff inside the PC to see if it was a current draw issue, but that had no effect; besides 2.6.8.1 works (although X got really really really slow and jerky for some reason).  I made sure all the CFLAGS were unset before compiling, and this is with gcc-3.4.1, as have been the past umpteen kernel builds for me.  I think I screwed up my system, or triggered some obscure bug, but please send any ideas my way, and CC gregdavis@ieee.org as I am not subscribed to the list.

Thanks,
Greg Davis
</blockquote>
