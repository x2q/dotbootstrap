---
layout: post
published: true
title: dos2unix on Ubuntu and Debian
permalink: /dos2unix-on-ubuntu-and-debian/
wordpress_id: 616
categories:
- News
- Linux
- Open Source
- Debian
- Ubuntu
- Windows
- Red Hat
- unix
- dos2unix
- convert
- plain text
- txt
- win32
- DoS
- dos2unix ubuntu
- ubuntu dos2unix
- dos2unix debian
- debian dos2unix
- ubuntu install dos2unix
- dos2unix tool
- dos2unix ubuntu package
---


DOS text files traditionally have a carriage return and line feed character as newline character or symbol - mostly for historic reasons i think. Unix and Linux on the other hand have a line feed character as newline character in text files - and Macs have yet another "standard".

From time to time I need to convert from one text file "standard" to another.

Red Hat-based Linux distributions are normally distributed with a small tool called dos2unix, which is able to do the conversion job very easy, but Debian-based Linux distributions like Debian itself and Ubuntu do not include the dos2unix tool by default.

The dos2unix tool i available in the Debian / Ubuntu package called <strong>tofrodos</strong>. To install the packages just type:  


```
aptitude install tofrodos
```



Once you have the tofrodos package installed you are able to use the dos2unix command from the command line, like this: 


```
dos2unix dosfile.txt
```


After running the command all the historic and crappy windows newlines are gone. ;)
