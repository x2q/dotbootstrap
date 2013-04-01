---
layout: post
published: true
title: The Top 20 Unix Shell Commands I Use
permalink: /the-top-20-unix-shell-commands-i-use/
wordpress_id: 291
categories:
- Links
- Linux
- unix
- IBM
- USD
- Unix Shell
---


A great <a href="http://en.wikipedia.org/wiki/One-liner_program">one-liner</a> from <a href="http://www.ibm.com/developerworks/aix/library/au-productivitytips.html">IBM UNIX productivity tips</a>:


```

bart$ history | awk '{print $2}' | awk 'BEGIN {FS="|"} {print $1}' | sort | uniq -c | sort -rn | head -20
     71 ls
     69 ./webplot.pl
     68 cd
     62 ps
     49 w
     49 lp
     26 ssh
     18 touch
     17 ping
     16 top
     16 make
     15 id
     14 wget
     13 toplp
     13 cat
     12 ./x86_64-softmmu/qemu-system-x86_64
     12 host
     11 mc
     11 man
      9 echo

```


<!--adsense#Referer-->
