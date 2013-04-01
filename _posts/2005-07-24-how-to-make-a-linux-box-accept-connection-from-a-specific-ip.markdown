---
layout: post
published: true
title: How to make a Linux box accept connection from a specific IP
permalink: /how-to-make-a-linux-box-accept-connection-from-a-specific-ip/
wordpress_id: 91
categories:
- News
- Linux
---



```

<blockquote>
iptables -A INPUT -p tcp -s 192.168.0.0/16 --dport 22 -j ACCEPT
</blockquote>

```


This would allow anything from the 192.168.0.0/16 segment, 192.168.0.20 e.g.
