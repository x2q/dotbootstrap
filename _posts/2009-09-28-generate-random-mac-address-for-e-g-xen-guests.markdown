---
layout: post
published: true
title: ! 'Generate random MAC address for e.g. Xen guests '
permalink: /generate-random-mac-address-for-e-g-xen-guests/
wordpress_id: 852
categories:
- News
- Xen
- Mac
- Python
- random mac address generator
- xen mac address generator
- random mac address
- generate random mac address
- MAC address
- generate mac address
---


The following tiny python script can be used to generates a MAC address for different purposes e.g. Xen guest.



<pre name="code" class="python">
#! /usr/bin/python
# macgen.py script generates a MAC address for Xen guests
#
import random
mac = [ 0x00, 0x16, 0x3e,
random.randint(0x00, 0x7f),
random.randint(0x00, 0xff),
random.randint(0x00, 0xff) ]
print ':'.join(map(lambda x: "%02x" % x, mac))

```
