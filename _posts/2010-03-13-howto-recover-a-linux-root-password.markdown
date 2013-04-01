---
layout: post
published: true
title: Howto Recover a Linux Root Password
permalink: /howto-recover-a-linux-root-password/
wordpress_id: 964
categories:
- News
- Linux
- Debian
- Ubuntu
- Crack
- hack
- recover
- root
- root password
- /etc/passwd
---


This post is intended for users that forgot the root passwords or can't use it due to other problems (corrupted file /etc/passwd or whatever). Can also be used to gain unauthorized to linux machines, but don't do that.


<strong>What to do</strong>
Boot using a recovery CD or DVD.

Mount the drive

```

mount /mnt /dev/sda2

```


Replace the existing root password with an empty one

```

sed /^root/s/.*:root:/root::0:0:root:/ /mnt/etc/passwd  

```



And reboot - and you are done ;-)
   

