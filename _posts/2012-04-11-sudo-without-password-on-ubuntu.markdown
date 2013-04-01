---
layout: post
published: true
title: Sudo without password on Ubuntu
permalink: /sudo-without-password-on-ubuntu/
wordpress_id: 2017
categories:
- Linux
- Howto
- Debian
- Ubuntu
- password
- sudo
---

```
sudo visudo
```


Add this line at the end (change "cc" to your username)
cc ALL=(ALL) NOPASSWD: ALL

Ctrl-X to leave, save your changes, and you're ready to sudo without password.
