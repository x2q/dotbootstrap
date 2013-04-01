---
layout: post
published: true
title: Howto Publish Weather Data from a LaCrosse 2300 Weather Station using a Linksys
  NSLU2 and Open2300
permalink: /howto-publish-weather-data-from-a-lacrosse-2300-weather-station-using-a-linksys-nslu2-and-open2300/
wordpress_id: 884
categories:
- Linux
- linksys
- xml
- LaCrosse
- Weather Station
- NSLU2
- Open2300
- pl2303
- openwrt
- upslug
- DMI
- Virtual Weather Station
- Weather Display
- Weatherlink
- XScale
- JFFS2
- power efficient solution
---


The LaCrosse 2300 Weather Station is a widespread and popular amateur weather station. This Howto outlines howto install and configure a LaCrosse 2300 Weather Station and Linksys NSLU2 to stream data to DMI, which is the agency that manages the meteorological, climatological and oceanographic services
to the society in Denmark, the Faeroe Islands and Greenland.

The hardware setup is as follows:

<ul>
	<li>LaCrosse 2300 Weather Station</li>
	<li>Linksys NSLU2</li>
	<li>PL-2303 USB to Serial Converter/Bridge (connects the Weather Station to the NSLU2)</li>
</ul>

Some may ask, why not just use a PC; desktop or HTPC and use the Windows software; Virtual Weather Station (VWS), Weather Display or Weatherlink. The reason is simple - a traditional PC makes noise and consumes too much power.

A lean, silent, and power efficient solution is required and here the Linksys NSLU2 comes into the game. A Linksys NSLU2 combined with the customized firmware OpenWrt is an incredible powerful and effective couple, which you can use for many interesting things e.g. SlimServer, uShare, iTunesServer, Asterisk, and a LAN/WAN digital camera server. Many different things, a more complete list is available <a href="http://www.nslu2-linux.org/wiki/Applications/HomePage">here</a>.

<strong>What is OpenWrt</strong>
OpenWrt is an open source project to create a free embedded operating system for network devices. Users wanting to use only internal flash memory to install the system should try OpenWrt. It has a large user community and is actively developped.

<strong>Anyway back to the configuration of the NSLU2.</strong>


<strong>Install UpSlug</strong>
UpSlug is a (Linux / MacOS X) tool to flash your NSLU2 from an external computer on the same subnet (direct Ethernet access is needed; it won't work if you have routers or NAT devices between you and the NSLU2. On Ubuntu 9.10 UpSlug2 is available in the repositories.


```

sudo aptitude install upslug2

```



<strong>Get The Stable OpenWrt Firmware Image</strong>


```

wget http://kamikaze.openwrt.org/8.09.1/ixp4xx/openwrt-nslu2-squashfs.bin

```




<strong>Set The NSLU2 Into Upgrade Mode</strong>
To do this, make sure the NSLU2 is turned off. Then press the reset button with a paper clip or small screwdriver and keep it pressed. Turn the NSLU2 on. The "Ready/Status" led will be yellow. When it changes to a red shade, immediately release the reset button. If it flashes red and green, you have succeeded (if not, unplug and try again).

Now upslug2 should find the nslu2 over the LAN and display the information. Install the image with upslug2 -i filename. It will flash and verify the upload and then reboot automatically.

Afterwards the NSLU2 will take a few minutes to initialize the JFFS2 partition, don't reboot if you cannot access it immediately. It will start up using the IP 192.168.1.1 and if that particular address is already taken then it will default to DHCP. Try telnet and ping to access it.

<strong>Install ssmtp, USB OHCI and pl2303 Kernel Drivers</strong>


```

root@nslu2:~# opkg update
root@nslu2:~# opkg install ssmtp kmod-usb-ohci kmod-usb-serial-pl2303

```


<strong>Install open2300</strong>
open2300 reads/writes data from the Lacrosse WS2300 family of weather stations. Includes tools that send data to: logfiles, webpages with graphs, XML file, MySQL, Weather Underground, Citizen Weather.

The open2300 is not available in the official OpenWrt package repository, however it can be compiled for the NSLU2 and OpenWrt from source using the OpenWrt and the open2300 source packages.


```
$ scp open2300_1.11-1.11_armeb.ipk root@192.168.1.1:
root@nslu2:~# opkg install open2300_1.11-1.11_armeb.ipk
```


<strong>Adjust open2300 Configuration</strong>

Adjust /etc/open2300.conf to the correct serial device ike this:


```
SERIAL_DEVICE                 /dev/ttyUSB0  # /dev/ttyS0, /dev/ttyS1, COM1, COM2 etc
```


<strong>Fetch Data From The Weather Station</strong>

```
root@nslu2:~# fetch2300 
Date 2009-Dec-29
Time 13:58:51
Ti 18.4
Timin 16.1
Timax 18.8
TTimin 00:46
DTimin 2001-01-01
TTimax 01:45
DTimax 2001-01-01
To 1.8
Tomin -3.4
Tomax 2.4
TTomin 06:03
DTomin 2001-01-01
TTomax 16:47
DTomax 2001-01-01
DP 0.1
DPmin -5.6
DPmax 0.8
TDPmin 04:09
DDPmin 2001-01-01
TDPmax 16:00
DDPmax 2001-01-01
RHi 38
RHimin 37
RHimax 48
TRHimin 17:22
DRHimin 2001-01-01
TRHimax 00:46
DRHimax 2001-01-01
RHo 89
RHomin 82
RHomax 90
TRHomin 00:48
DRHomin 2001-01-01
TRHomax 16:00
DRHomax 2001-01-01
WS 0.0
DIRtext WNW
DIR0 292.5
DIR1 292.5
DIR2 292.5
DIR3 292.5
DIR4 292.5
DIR5 292.5
WC 1.8
WCmin -3.4
WCmax 2.4
TWCmin 06:03
DWCmin 2001-01-01
TWCmax 16:47
DWCmax 2001-01-01
WSmin 0.0
WSmax 2.2
TWSmin 17:26
DWSmin 2001-01-01
TWSmax 10:52
DWSmax 2001-01-01
R1h 0.00
R1hmax 0.51
TR1hmax 17:16
DR1hmax 2001-01-01
R24h 0.51
R24hmax 0.51
TR24hmax 17:21
DR24hmax 2001-01-01
Rtot 15.01
TRtot 12:12
DRtot 2008-06-08
RP 990.400
RPmin 988.400
RPmax 991.000
TRPmin 00:21
DRPmin 2001-01-01
TRPmax 15:07
DRPmax 2001-01-01
Tendency Steady
Forecast Cloudy
```





<strong>Upload Data to DMI Borgervejr, Citizens Weather, and Weather Underground</strong>


<strong>DMI Borgervejr</strong>

Create a bash script like this:
```
#!/bin/sh
log2300 /tmp/open2300.log
echo "" > /tmp/mail.txt
date '+%d/%m/%Y %H:%M:%S' >> /tmp/mail.txt
tail -n 1 /tmp/open2300.log | awk '{print "Humidity: " $8 "%\n" "Temp: " $5 "C\n" "Raw Barom: " $16 "hPa\n" "Wind Dir: " $10 "\n" "Wind Spd: " $9 "mps\n" "Wind Gust: " $9 "mps\n" "Tot Rain: " $15 "mm\n"}' >> /tmp/mail.txt
cat /tmp/mail.txt | ssmtp borgervejr@dmi.dk
rm -rf /tmp/open2300.log
rm -rf /tmp/mail.txt
```
