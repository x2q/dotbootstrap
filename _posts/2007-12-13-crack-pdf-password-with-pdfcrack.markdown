---
layout: post
published: true
title: Crack pdf password with pdfcrack
permalink: /crack-pdf-password-with-pdfcrack/
wordpress_id: 557
categories:
- Links
- Linux
- Open Standards
- Open Source
- Debian
- Ubuntu
- Fedora
- security
- pdf
- GNU/Linux
- pdf password linux
- pdfcrack
- pdf crack linux
- PDF Password Remover linux
- fileopen crack
- POSIX
---


<a href="http://pdfcrack.sourceforge.net/">PDFCrack</a> is a GNU/Linux application (or any other POSIX-compatible system) tool for recovering passwords and content from <a href="http://en.wikipedia.org/wiki/Portable_Document_Format">PDF</a>-files. It is small, command line driven without external dependencies. PDFCrack is released under <a href="http://www.gnu.org/copyleft/gpl.html">GPL</a>.

Install and pdfcrack on Ubuntu by typing:

```

cc@zeus:~$ sudo aptitude install pdfcrack

```


Run a quick cracking power benchmark:

```

cc@zeus:~/Desktop$ pdfcrack -b
Benchmark:      Average Speed (calls / second):
MD5:                    1728972.6
MD5_50 (fast):          97879.3
MD5_50 (slow):          69167.0

RC4 (40, static):       606555.3
RC4 (40, no check):     598050.0
RC4 (128, no check):    590141.7




Benchmark:      Average Speed (passwords / second):
PDF (40, user):         453510.2
PDF (40, owner):        220250.0
PDF (40, owner, fast):  499995.0

PDF (128, user):        22000.0
PDF (128, owner):       10408.7
PDF (128, owner, fast): 22220.0
cc@zeus:~/Desktop$ 

```


Use the pdfcrack to crack an encrypted pdf-file by typing:

```

cc@zeus:~/Desktop$ pdfcrack test.pdf

```




Happy pdf-hacking and cracking
