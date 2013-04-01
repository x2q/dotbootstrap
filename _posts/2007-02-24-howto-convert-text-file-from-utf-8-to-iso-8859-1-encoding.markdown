---
layout: post
published: true
title: Howto Convert Text File From UTF-8 to ISO-8859-1 Encoding
permalink: /howto-convert-text-file-from-utf-8-to-iso-8859-1-encoding/
wordpress_id: 357
categories:
- Links
- Linux
- Open Standards
- Open Source
- Debian
- Ubuntu
- java convert encoding
- linux convert file encoding
- convert file encoding
- linux convert to utf8
- linux convert character encoding
---


Convert a iso-8859-1 charset file into a utf-8 charset file using standard Linux tools.

The solution - using <a href="http://en.wikipedia.org/wiki/Bash">bash shell</a> and using <a href="http://en.wikipedia.org/wiki/Linux">Linux</a> - of course:


```

iconv --to-code=ISO-8859-1 --from-code=UTF-8 utf.txt > iso.txt

```


And reverse


```

iconv --from-code=ISO-8859-1 --to-code=UTF-8 iso.txt > utf.txt

```
