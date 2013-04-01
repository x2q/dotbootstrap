---
layout: post
published: true
title: Use of diff and patch
permalink: /use-of-diff-and-patch/
wordpress_id: 94
categories:
- News
- patch.diff a64:/usr/src/software/oldversion# patch
- patch a64:/usr/src/software# diff
- ubuntu patch diff
---



```

a64:/usr/src/software# diff -rud oldversion/ newversion/ >> patch.diff
a64:/usr/src/software/oldversion# patch -p1 < ../patch.diff

```
