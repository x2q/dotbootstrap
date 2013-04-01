---
layout: post
published: true
title: Recursive search and replace
permalink: /recursive-search-and-replace/
wordpress_id: 119
categories:
- Links
- Linux
- perl
---



```
find . -type f -print | xargs perl -i.bak -pe 's/searchString/replaceString/g';
```


Taken from <a href="http://www.sslug.dk/julekalender/2000/13.php3">SSLUG's Julekalender 2000</a>
