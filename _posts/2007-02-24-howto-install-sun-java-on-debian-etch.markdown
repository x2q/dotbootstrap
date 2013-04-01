---
layout: post
published: true
title: Howto Install Sun Java on Debian Etch
permalink: /howto-install-sun-java-on-debian-etch/
wordpress_id: 359
categories:
- Links
- Linux
- Open Standards
- Debian
- Ubuntu
- Java
- debian install java
- java debian etch
- debian etch java
- install java debian
- install java debian etch
---


<img align="right" id="image358" src="http://lh5.ggpht.com/-u_DQUShZwYk/UVl9uDsvIvI/AAAAAAAAFmg/n1PB30P1qyk/java.png" alt="Java Logo" />This small guide shows how to install the original <a href="http://www.oracle.com/technetwork/java/index.html">Sun Java</a> <a href="http://en.wikipedia.org/wiki/Java_Platform%2C_Standard_Edition">2 Platform Standard Edition 5.0 JRE</a> (Java Runtime Environment) and JDK (Java Developer Kit) on <a href="http://wiki.debian.org/DebianEtch">Debian 4.0 Etch
</a>.

The original Sun Java 2 is available in the 'non-free' section of the <a href="http://www.debian.org/">Debian</a> repositories. To enable this section first add the non-free repository to the apt sources file - the /etc/apt/sources.list should look like, - important parts are in bold:


```

deb http://ftp.us.debian.org/debian/ etch main <strong>contrib non-free</strong>

```


Now, update apt:

```

sudo apt-get update

```




Then install the Java debian packages. 

```

sudo apt-get install sun-java5-jre

```


Or this for installing the JDK ( the Java SDK )

```

sudo apt-get install sun-java5-jdk

```


