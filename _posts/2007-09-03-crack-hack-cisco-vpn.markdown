---
layout: post
published: true
title: Crack Cisco VPN (hack)
permalink: /crack-hack-cisco-vpn/
wordpress_id: 510
categories:
- Links
- Linux
- Open Source
- Debian
- Ubuntu
- Crack
- security
- hack
- xp
- cisco
- Mac OS X
- Wireless Network
- VPN
- author
- Twin author
- original author
- foreign network
- vpn hack
- hack vpn
- cisco vpn shared secret
- cisco shared secret decoder
- cisco vpn password cracker
---


This guide walks through a setup to break into a Cisco VPN protected wireless network. The guide describes how to install and configure a fake access-point and further how to crack the Cisco VPN authentication and get usernames and passwords in plain text, in real time. The author of the attack Cisco VPN crack has named the attack method &acirc;&euro;&oelig;Evil Twin&acirc;&euro;. The guide is described <a href="http://folk.ntnu.no/">here</a> by its original author.

Requirements and need in order to make a successful crack according to the Evil Twin author.

<ol>

	<li>A public, open network (where VPN are used with IKE/ISAKMP aggressive mode)</li>

	<li>The VPN shared secret and IP address and/or domain name</li>

	<li>A box running some kind of Linux flavor (Ubuntu is a winner)</li>
	<li>A box running XP of OS X, so you can run the Cisco VPN client, or if you prefer, run some other client that permits aggressive mode on the Linux box</li>

	<li><strong>Optionally</strong> you can use a seperate access point instead of using the linux box to pose as one(I have tested Linksys WRT54G with original firmware)
</li>




	<li>The Cisco VPN client. You can use any other client that allows aggressive mode (check out VPNC), but since the Cisco client is quite widespread, testing has been perfomed using it.</li>

	<li>Openswan source code (The opensource VPN server, Version 2.3.0 seems to work)</li>

	<li>Patch for Openswan 2.3.0</li>


</ol>


<strong>DISCLAIMER</strong>: You should only use this guide or tutorial to crack your own network. This guide or tutorial is not a guide for cracker or hackers with intentions to hack or crack a foreign network. This is intended educational. Remember it is your own responsibility not to do any crimes.
