---
layout: post
published: true
title: Howto Use URL Rewriting for PHP Web Applications
permalink: /howto-use-url-rewriting-for-php-web-applications/
wordpress_id: 400
categories:
- News
- Linux
- Search Engine Optimization
- apache
- PHP
- SEO
- mod_rewrite
- web applications
- USD
- url rewriting in php
- url rewriting php
- php url rewriting
- php url rewrite
- url rewrite php
---

```

Options +FollowSymlinks
RewriteEngine on
RewriteRule ^files/(.+)/(.+).tar.gzip download.php?section=$1&file=$2 [nc]

```


Would allow you to present a link as:
http://site.com/files/games/bubble.tar.gzip

and in the background have that translated to..
http://site.com/download.php?section=games&file=bubble


