---
layout: post
published: true
title: Howto install Sun Java on Debian Sarge
permalink: /howto-install-sun-java-on-debian-sarge/
wordpress_id: 168
categories:
- News
- Linux
- Java
- Reading
- Sun Microsystems Inc.
- java deb download
- java deb
- No matching plugin was found
- dpkg-reconfigure java
---
This small guide shows Howto install the original Sun Java 2 Platform Standard Edition 5.0 JRE (Java Runtime Environment) and JDK (Java Developer Kit) on Debian 3.1 (Sarge)

First of all we'll need to download the latest Sun Java release from <a href="http://www.oracle.com/technetwork/java/index.html">java.sun.com</a>.

Download the file called "Linux self-extracting file"  - "jdk-1_5_0_06-linux-i586.bin"

Now we need to use some utilities to convert the self-extracting file into a debian package.

```

debian:~# apt-get install fakeroot java-package
Reading Package Lists... Done
Building Dependency Tree... Done
The following NEW packages will be installed:
  fakeroot java-package
0 upgraded, 2 newly installed, 0 to remove and 11 not upgraded.
Need to get 0B/90.1kB of archives.
After unpacking 471kB of additional disk space will be used.
Selecting previously deselected package fakeroot.
(Reading database ... 42761 files and directories currently installed.)
Unpacking fakeroot (from .../fakeroot_1.2.10_i386.deb) ...
Selecting previously deselected package java-package.
Unpacking java-package (from .../java-package_0.24_all.deb) ...
Setting up fakeroot (1.2.10) ...

Setting up java-package (0.24) ...
debian:~#

```


And then we are ready to covert the self-extracing bin file into a debian package.


```

user@debian:~$ fakeroot make-jpkg jdk-1_5_0_06-linux-i586.bin
Creating temporary directory: /tmp/make-jpkg.XXXXZf6Frs
Loading plugins: blackdown-j2re.sh blackdown-j2sdk.sh common.sh ibm-j2re.sh ibm-j2sdk.sh j2re.sh j2sdk.sh j2se.sh sun-j2re.sh sun-j2sdk.sh

Detected product:
    Java(TM) Software Development Kit (J2SDK)
    Standard Edition, Version 1.5.0+update06
    Sun Microsystems(TM), Inc.
Is this correct [Y/n]:

```


Then we accept all the legal stuff and now the have just a single deb

```

The Debian package has been created in the current directory. You can
install the package as root (e.g. dpkg -i sun-j2sdk1.5_1.5.0+update06_i386.deb).


Removing temporary directory: done

```



Now install the newly created deb as root by typing

```

debian:~# dpkg -i sun-j2sdk1.5_1.5.0+update06_i386.deb

```



```

user@debian:~$ java -version
java version "1.5.0_06"
Java(TM) 2 Runtime Environment, Standard Edition (build 1.5.0_06-b05)
Java HotSpot(TM) Client VM (build 1.5.0_06-b05, mixed mode, sharing)

```


