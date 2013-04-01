---
layout: post
published: true
title: ! 'Howto: Packet Sniffer/HTTP(s) From Router To PC/Mac'
permalink: /howto-packet-snifferhttps-router-pcmac/
wordpress_id: 1947
categories:
- Linux
- Open Source
- Howto
- Mac
- etc
- sniff
- http
- tcp
- software
- network
- openwrt
- firmware
- root
- firewall
- computers
- Packet Sniffer
- PC
- WRT
- DD
- IRC
- RADIUS
- CPE
---
From time to time you'll need to sniff and reverse engineer certain things, e.g. I am wanting to packet sniff all instant messages (MSN, AIM, IRC, Facebook Meesages, FbIM, etc).

It is possible to put together an advanced devices using linux, iptables, etc, however most people already got a fairly useful device - the dd-wrt or openwrt based router/firewall. 

In case you got a DD-WRT or OpenWrt-based router/firewall, then you should be able to use one of the following one liner example command lines:

Simple packet sniffing on the switch
    
```

	 ssh -x root@192.168.11.1 <br />
	 root@DD-WRT:~# tcpdump -i br0
    
```

Simple packet sniffing on port 3 of the switch
    
```

	 ssh -x root@192.168.11.1 <br />
	 root@DD-WRT:~# tcpdump -i vlan13 <br />
    
```

Packet sniffing as a single remote command. Note that full path to executables and library is required
    
```

	 ssh -x root@192.168.11.1 /sbin/tcpdump 'not tcp port 22' -i br0<br />
    
```

Remote command packet sniffing with raw packet dump to a local file.

This command will do a remote packet capture on the switch and save the raw packet data on the local PC, where it can be analysed with <a href="http://www.wireshark.org">Wireshark</a> or other tools.
    
```

	 ssh -x root@192.168.11.1 /sbin/tcpdump 'not tcp port 22' -i br0 -s0 -U -w - > dump.pcap<br />
    
```

If you're using linux on your PC then you can pipe the raw tcpdump capture into a Wireshark running on the local PC and get live analysis of the data
    
```

	 ssh -x root@192.168.11.1 /sbin/tcpdump 'not tcp port 22' -i br0 -s0 -U -w - | wireshark -k -i - <br />
    
```

And, my favorite, piping the raw packet data into <a href="http://etherape.sourceforge.net/">Etherape</a> for a live graphical representation of the network traffic<br />
    
```

	 ssh -x root@192.168.11.1 /sbin/tcpdump 'not tcp port 22' -i br1 -s0 -U -w - | etherape -r - <br />
    
```

<strong>What is DD-WRT</strong>
DD-WRT is a Linux-based firmware for several wireless routers, most notably the Linksys WRT54G (including the WRT54GL and WRT54GS). Like other similar projects, DD-WRT is third-party firmware designed to replace the firmware that ships pre-installed on many commercial routers. This is done for a variety of reasons including the addition of features which are not typically included in a manufacturer's router firmware.
DD-WRT includes such features as support for the Kai network, daemon-based services, IPv6, Wireless Distribution System, RADIUS, advanced quality of service, radio output power control, overclocking capability, and software support for a Secure Digital card hardware modification.
Buffalo Technology and other companies have shipped routers pre-installed with a customized version of DD-WRT.

<strong>What is OpenWrt</strong>
OpenWrt is a Linux distribution primarily targeted at routing on embedded devices. It comprises a set of about 2000 software packages, installed and uninstalled via the opkg package management system. OpenWrt can be configured using the command-line interface of BusyBox ash, or the web interface LuCI.
OpenWrt can be run on CPE routers, residential gateways, smartphones (e.g. Neo FreeRunner), pocket computers (e.g. Ben NanoNote), and small laptops (e.g. One Laptop per Child (OLPC)). But it is also possible to run on ordinary computers (e.g. x86).

List of devices with built-in sniffing support can be found here: <a href="http://wiki.openwrt.org/toh/start">http://wiki.openwrt.org/toh/start</a> and <a href="http://www.dd-wrt.com/wiki/index.php/Supported_Devices">http://www.dd-wrt.com/wiki/index.php/Supported_Devices</a>.

