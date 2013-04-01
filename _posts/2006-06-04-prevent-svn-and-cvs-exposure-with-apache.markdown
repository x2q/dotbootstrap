---
layout: post
published: true
title: Prevent SVN and CVS exposure with Apache
permalink: /prevent-svn-and-cvs-exposure-with-apache/
wordpress_id: 254
categories:
- News
- Linux
- apache
- CVS
- apache prevent svn
---



```

<Directorymatch "^/.*/\.svn/">
        Order deny,allow
        Deny from all
</Directorymatch>

```
