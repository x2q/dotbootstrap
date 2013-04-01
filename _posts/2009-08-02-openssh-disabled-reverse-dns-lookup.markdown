---
layout: post
published: true
title: ! 'OpenSSH: Disabled Reverse DNS Lookup'
permalink: /openssh-disabled-reverse-dns-lookup/
wordpress_id: 817
categories:
- News
- SSH
- performance
- OpenSSH
- DNS
- Reverse DNS Lookup
- ssh reverse dns
---


The post is mostly to myself, but hopefully useful for others too.

When connecting to an OpenSSH server, one of the first things that the server does is to perform a reverse DNS loopuk on the client's IP, which is in general a slow operation and causing for an unnecessary delay during authentication. However this reverse DNS lookup can be disabled. 

Do the following to disable it:

```

# In /etc/ssh/sshd_config:
UseDNS no

```
