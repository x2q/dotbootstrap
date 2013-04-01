---
layout: post
published: true
title: ! 'HackerGuide: Syn-Flood Attack'
permalink: /hackerguide-syn-flood-attack/
wordpress_id: 610
categories:
- News
- Linux
- Debian
- Ubuntu
- security
- cracking
- DoS
- TCP/IP protocol
- security auditing
- syn flood attack
- syn flood tool
- hping syn flood
- syn flood
- how to syn flood
---


<strong>Warning: Malicious use of SYN-floods are punishable by law.</strong>

This post shows howto to establish a synflood attack on an arbitrary remote host. The attack is performed using <a href="http://en.wikipedia.org/wiki/Hping">hping</a>, which is free packet generator and analyzer for the TCP/IP protocol. Hping is one of the de facto tools for security auditing and testing of firewalls and networks. A syn-flood attack is basically a DOS-attack on a bug in TCP - some will argue that TCP is defective by design ;)

The actual attack is initialized by this command:

```

hping -i u1 -S -p 80 dst-host-or-ip

```


<strong>In most cases DoS attacks like this one renders a webserver totally unable to serve any requests from users.</strong>


To get hping installed on a Debian or Ubuntu-based system, type this to install:


```
aptitude install hping2
```
