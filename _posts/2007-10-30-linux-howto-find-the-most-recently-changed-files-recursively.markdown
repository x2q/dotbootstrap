---
layout: post
published: true
title: ! 'Linux Howto: Find the most recently changed files (recursively)'
permalink: /linux-howto-find-the-most-recently-changed-files-recursively/
wordpress_id: 541
categories:
- News
- Linux
- Open Source
- Debian
- Ubuntu
- Fedora
- linux find recent files
- linux find recently modified files
- linux find most recently modified file
- linux find newest file
- find recent files linux
---



```

find . -type f -printf "%TY-%Tm-%Td %TT %p\n" | sort | less

```
