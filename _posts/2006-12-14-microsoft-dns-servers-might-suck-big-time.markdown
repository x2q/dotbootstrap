---
layout: post
published: true
title: Microsoft DNS Servers Might Suck Big Time
permalink: /microsoft-dns-servers-might-suck-big-time/
wordpress_id: 332
categories:
- Links
- Linux
- DNS
- ISP
---


<blockquote>
Dec 12: It appears that a large number of users preferentially hit server 1, despite DNS round-robin. Some reports indicate that this may be caused when there is a Microsoft DNS server in between us and the end user (e.g. at the ISP.) Therefore, if you use rsync against our servers, you may want to hit server 2 explicitly (rsync2.kernel.org or mirrors2.kernel.org).
</blockquote>

<a href="https://www.kernel.org/">Quote from kernel.org</a>
