---
layout: post
published: true
title: Crack zip password with fcrackzip
permalink: /crack-zip-password-with-fcrackzip/
wordpress_id: 556
categories:
- Links
- Linux
- Open Standards
- Open Source
- Debian
- Ubuntu
- Fedora
- Crack
- security
- hack
- encryption
- pdf
- crack zip password
- fcrackzip
- hack zip password
- break zip password
- crack zip file
---


<a href="http://oldhome.schmorp.de/marc/fcrackzip.html">fcrackzip</a> is a zip-file encryption cracker, which can handle (crack / hack) any password encrypted zipfile. Inside it uses a number of methods to accomplish the crack, but this happens nicely behind the scenes.

Install and fcrackzip on Ubuntu by typing:

```

cc@zeus:~$ sudo aptitude install fcrackzip

```


Use the fcrackzip for password cracking on Ubuntu by typing:

```

cc@zeus:~/Desktop$ fcrackzip -v -b -p aaaa -u cuda_dxtc.pdf.zip 
found file 'cuda_dxtc.pdf', (size cp/uc 244965/294438, flags 9, chk a5d3)
checking pw rUt~                                    



PASSWORD FOUND!!!!: pw == test
cc@zeus:~/Desktop$ 

```


Happy zip-file cracking ;)


<a href="http://oldhome.schmorp.de/marc/fcrackzip.html">FCrackZip website</a>
