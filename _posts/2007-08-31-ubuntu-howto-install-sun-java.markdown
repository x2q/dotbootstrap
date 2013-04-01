---
layout: post
published: true
title: ! 'Ubuntu Howto: Install Sun Java'
permalink: /ubuntu-howto-install-sun-java/
wordpress_id: 499
categories:
- News
- Linux
- Open Standards
- Open Source
- Ubuntu
- Java
- ubuntu sun java
- sun java ubuntu
- ubuntu install sun java
- java ubuntu 9
- install sun java ubuntu
---


<img align="right" id="image358" src="http://lh3.ggpht.com/-3GIlRiA9NQs/UVl_J6VyEDI/AAAAAAAAFuQ/-2NZ4kWnu8k/java.png" alt="Java Logo" />This small guide shows how to install the original <a href="http://www.oracle.com/technetwork/java/index.html">Sun Java</a> <a href="http://en.wikipedia.org/wiki/Java_Platform%2C_Standard_Edition">2 Platform Standard Edition 5.0 JRE</a> (Java Runtime Environment) and JDK (Java Developer Kit) on <a href="http://wiki.debian.org/Ubuntu">Ubuntu</a>.

The original Sun Java 2 is available in the 'multiverse' section of the <a href="http://packages.ubuntu.com/">Ubuntu</a> repositories. To enable this section first add the multiverse repository to the apt sources file - the /etc/apt/sources.list should look like, - important parts are in bold:


```

deb http://dk.archive.ubuntu.com/ubuntu/  feisty <strong>universe multiverse</strong>

```


Now, update apt:

```

sudo apt-get update

```


Then install the Java debian packages. 

```

sudo apt-get install sun-java5-bin

```


Or this for installing the JDK ( the Java SDK )

```

sudo apt-get install sun-java5-jdk

```


