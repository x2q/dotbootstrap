---
layout: post
published: true
title: How To Enable Telnet On A Samsung TV
permalink: /how-to-enable-telnet-on-a-samsung-tv/
wordpress_id: 887
categories:
- News
- Linux
- Java
- Samsung
- gpl
- telnet
- firmware
- TV
- Samsung TV
- samsung 6 series
- samsung 7 series
- samsung 8 series
- Samsung LED
- LED
- Samsung DLNA
- Harvard
- Content Library
- samsung content library download
---
The recent set of Samsung TV firmware is based on the Linux Kernel, which mean that it is possible to research and enhance your own Samsung TV. Pretty fancy.



The list of Linux-based Samsung TVs is available <a href="http://sourceforge.net/apps/mediawiki/samygo/index.php?title=Compatibility">here</a>.

<strong>How To Enable Telnet On A Samsung TV</strong>

<em>Reminder: Enabling telnet with this program is not dangerous but with wrong telnet commands, still you have a chance to brick your TV.
</em>

Download SamyGO Telnet Enabler Samsung TV application from <a href="http://sourceforge.net/projects/samygo/files/">SourceForge</a>.

Copy the SamyGO Telnet Enabler Samsung TV application to a USB Flash, then plug it into your TV. Using the Content Library from the Pup-Up menu, select USB, then under Game menu, select and start the SamyGO application once. The TV will then turn into black and then return to the menu. This will enable a telnet session on the Samsung TV. When you reboot your TV (switch off and back on) you need to reopen telnet via the menu.

Now you are able to telnet to your Samsung TV.


```

$ telnet 192.168.2.11

```


Take a look around e.g. at /proc/cpuinfo


```

# cat /proc/cpuinfo 
Processor       : ARMv6-compatible processor rev 7 (v6l)
BogoMIPS        : 599.65
Features        : swp half fastmult vfp edsp java 
CPU implementer : 0x41
CPU architecture: 6TEJ
CPU variant     : 0x0
CPU part        : 0xb76
CPU revision    : 7
Cache type      : write-back
Cache clean     : cp15 c7 ops
Cache lockdown  : format C
Cache format    : Harvard
I size          : 16384
I assoc         : 4
I line length   : 32
I sets          : 128
D size          : 16384
D assoc         : 4
D line length   : 32
D sets          : 128

Hardware        : Samsung-SDP83 Eval. Board(64bit 512MB)
Revision        : 0000
Serial          : 0000000000000000

```

