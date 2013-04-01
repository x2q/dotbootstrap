---
layout: post
published: true
title: Howto use WEP encryption with Ubuntu Linux
permalink: /howto-use-wep-encryption-with-ubuntu-linux/
wordpress_id: 194
categories:
- Links
- Linux
- Open Standards
- Open Source
- Ubuntu
- WEP
- wireless networks
- Howto use WEP encryption
- ubuntu wep
- wep ubuntu
- linux wep
- ubuntu wireless WEP
- wep linux
---


<img align="right" id="image283" src="http://lh3.ggpht.com/-CUrQB6ApnPQ/UVl87JVpwPI/AAAAAAAAFhA/EzFpjnUSzfE/thumb-gdm.png" alt="Ubuntu 6.10 Edgy login screen" />
Most <a href="http://www.ubuntu.com/">Ubuntu</a> versions support connecting to wep-encrypted wireless networks. Here a brief howto on wep and <a href="http://www.ubuntu.com/">Ubuntu</a>. First a hard way-method using command line and then a more easy and more user friendly method below.
<br />

<br />

<br />
  
<strong>The hard way:</strong>


```

cc@ubuntu:~$ sudo iwconfig eth2 essid MyNet
cc@ubuntu:~$ sudo iwconfig eth2 key xxxxxxxxxx
cc@ubuntu:~$ sudo ifconfig eth2 up
cc@ubuntu:~$ sudo dhclient3 eth2

```


And then ready to surf...


<strong>The easy way:</strong>
Install <a href="http://projects.gnome.org/NetworkManager/">NetworkManager</a>


```

cc@atlas:~$ sudo apt-get install NetworkManager

```
 

