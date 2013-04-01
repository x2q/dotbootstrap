---
layout: post
published: true
title: Gnome NetworkManagerInfo applet
permalink: /gnome-networkmanagerinfo-applet/
wordpress_id: 11
categories:
- News
- Wireless Network
---


<img src="http://lh3.ggpht.com/-d9KrFDjAJKc/UVl8ArOHXtI/AAAAAAAAFaw/P5ubtOS146c/screenshot-networkmanagerinfo-applet.png" border="0" alt="NetworkManagerInfo applet" />

Now I have been using Gnome NetworkManagerInfo applet for a few days, but it doesn't work as well as I thought it would. When I try to connect to a wireless network, it keeps running and running without getting connected at all. The only way I'm able to stop it is with:


```
/etc/init.d/NetworkManager stop
```


Afterwards it's possible to do a


```
/etc/init.d/network restart
```


Just to get back on the wired net.

Hopefully the NetworkManager team is in business to fix these very annoying problems.
