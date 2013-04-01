---
layout: post
published: true
title: /dev/rtc error with Ubuntu and Linux Kernel 2.6
permalink: /devrtc-error-with-ubuntu-and-linux-kernel-26/
wordpress_id: 195
categories:
- Links
- Linux
- Ubuntu
- ubuntu rtc
- ubuntu /dev/rtc
---
<strong>To avoid errors like this:</strong>

```

open(/dev/rtc) failed: No such file or directory

```


<strong>I created a link from /dev/rtc to /dev/.static/dev/rtc</strong>

```

sudo ln -s /dev/.static/dev/rtc /dev/rtc

```


