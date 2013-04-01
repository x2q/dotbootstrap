---
layout: post
published: true
title: Howto Wiretap - Sniff Network Traffic
permalink: /howto-wiretap-sniff-network-traffic/
wordpress_id: 535
categories:
- Links
- Linux
- Open Source
- Vista
- Debian
- Ubuntu
- Fedora
- Crack
- MySQL
- ssl
- cisco
- http
- DNS
- LAN
- UDP
- SNMP
- Local Area Networks
- software application
- GRE sniffing
- linux sniff network traffic
- ettercap howto
- sniff router traffic
---


From time to time I need a mechanism for wiretapping networks for packet analysis. For that purpose I use a software application called <a href="http://ettercap.sourceforge.net/">Ettercap NG</a>, which is a suite for <a href="http://en.wikipedia.org/wiki/Man-in-the-middle_attack">man in the middle attacks on LAN</a> (Local Area Networks), <a href="http://en.wikipedia.org/wiki/ARP_poisoning">ARP Poisoning</a>, and <a href="http://en.wikipedia.org/wiki/ARP_spoofing">ARP Spoofing</a>. It features sniffing of live connections, content filtering on the fly and many other interesting networks tricks, cracks and hacks. It supports active and passive dissection of many protocols (even ciphered ones, like SSL and SSH) and includes many feature for network and host analysis.

This is the current list of Ettercap NG features.
<ul>
	<li>Character injection into an established connection: characters can be injected into a server (emulating commands) or to a client (emulating replies) while maintaining a live connection.</li>
	<li>SSH1 support: the sniffing of a username and password, and even the data of an SSH1 connection. Ettercap is the first software capable of sniffing an SSH connection in full duplex.</li>
	<li>HTTPS support: the sniffing of HTTP SSL secured data--even when the connection is made through a proxy.</li>
	<li>Remote traffic through a GRE tunnel: the sniffing of remote traffic through a GRE tunnel from a remote Cisco router, and perform a man-in-the-middle attack on it.</li>
	<li>Password collectors for: TELNET, FTP, POP, rlogin, SSH1, ICQ, SMB, MySQL, HTTP, NNTP, X11, Napster, IRC, RIP, BGP, SOCKS 5, IMAP 4, VNC, LDAP, NFS, SNMP, Half-Life, Quake 3, MSN, YMSG - password collectors sniffers makes it easy to acquire password from hosts and users conneted to the network.</li>

	<li>Packet filtering/dropping: setting up a filter that searches for a particular string (or hexadecimal sequence) in the TCP or UDP payload and replaces it with a custom string/sequence of choice, or drops the entire packet.</li>


	<li>Hijacking of DNS(Domain Name System) requests. . Useful feature for replacing given domains with others, e.g. hotmail.com with hotmale.com :)</li>

</ul>



<a href="http://ettercap.github.com/ettercap/">Download ettercap NG here</a>

Or read more on Ettercap NG <a href="http://en.wikipedia.org/wiki/Ettercap_%28computing%29">here</a>

<a href="http://ettercap.github.com/ettercap/">ARP Poisoning HowTo using Ettercap NG</a>
