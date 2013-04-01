---
layout: post
published: true
title: Howto install Java on Debian Sarge
permalink: /howto-install-java-on-debian-sarge/
wordpress_id: 161
categories:
- News
- Linux
- Java
- ftp://ftp.tux.org/java/debian
---
Add this line to your /etc/apt/sources.list file

```

 deb ftp://ftp.tux.org/java/debian/ sarge non-free

```


Run 'apt-get update'
Run 'apt-get install j2sdk1.4' to install the SDK or 'apt-get install j2re1.4' to install the Runtime Environment. 



