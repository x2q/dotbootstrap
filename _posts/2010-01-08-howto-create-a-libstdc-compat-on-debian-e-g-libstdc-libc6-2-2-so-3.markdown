---
layout: post
published: true
title: Howto Create a libstdc++ Compat on Debian (e.g. libstdc++-libc6.2-2.so.3)
permalink: /howto-create-a-libstdc-compat-on-debian-e-g-libstdc-libc6-2-2-so-3/
wordpress_id: 907
categories:
- News
- Linux
- Debian
- Ubuntu
- etch
- lenny
- firmware
- libstdc++
- rpm
- deb
- ldd
- ldconfig
- HP
- DL380
- G4
- Smart Array 6400
- ROM Flash
- controller
- crap software
- Online ROM Flash Component
---


Today I tried to update a Smart Array 6400 controller with a new firmware version, but it was not easy, since HP releases proprietary crap software, which is linked against an ancient version of the libstdc++ library, namely libstdc++-libc6.2-2.so.3.

This was, what I got using ldd 

```

hopper:~# ldd cpqsetup
	linux-gate.so.1 =>  (0xf7f4d000)
	libpthread.so.0 => /lib32/libpthread.so.0 (0xf7f2c000)
	libstdc++-libc6.2-2.so.3 => not found
	libm.so.6 => /lib32/libm.so.6 (0xf7ec6000)
	libc.so.6 => /lib32/libc.so.6 (0xf7d73000)
	/lib/ld-linux.so.2 (0xf7f4e000)
	libgcc_s.so.1 => /usr/lib32/libgcc_s.so.1 (0xf7d66000)

```


This solution is a follows:

Not pretty, but it works quite well with the HP Firmware CD Supplemental Update / Online ROM Flash Component for Linux - Smart Array 6400


```

wget compat-libstdc++-296-2.96-138.i386.rpm
aptitude install rpm
rpm2cpio compat-libstdc++-296-2.96-138.i386.rpm | cpio -idmv
export LD_LIBRARY_PATH=/root/usr/lib/:$LD_LIBRARY_PATH
ldconfig

```


Then ldd should show this:

```

hopper:~# ldd cpqsetup
	linux-gate.so.1 =>  (0xf7f4d000)
	libpthread.so.0 => /lib32/libpthread.so.0 (0xf7f2c000)
	libstdc++-libc6.2-2.so.3 => /root/usr/lib/libstdc++-libc6.2-2.so.3 (0xf7eea000)
	libm.so.6 => /lib32/libm.so.6 (0xf7ec6000)
	libc.so.6 => /lib32/libc.so.6 (0xf7d73000)
	/lib/ld-linux.so.2 (0xf7f4e000)
	libgcc_s.so.1 => /usr/lib32/libgcc_s.so.1 (0xf7d66000)

```


And then I was able to use the HP firmware update utility for Linux:

```

hopper:~# ./cpqsetup 
Firmware CD Supplemental Update / Online ROM Flash Component for Linux - Smart Array 6400
* Version of rom to be flashed: 2.84
* Number of controllers: 1
* The version of existing Array ROM is 2.80
* 1 controller(s) will be flashed
* This operation may take about 2 minutes
Flash ROMs Now? (Yes/No): Yes
Flashing 1 controller(s), please wait....
Success:  Product 409c0e11 at controller position 0
with old version 2.80 has been updated with new version 2.84.
ROM Flash complete.  New firmware will take effect when the server is rebooted.
As part of the reboot process, you should power cycle the server and any
external drive arrays.

```
