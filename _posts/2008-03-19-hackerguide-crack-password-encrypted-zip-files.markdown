---
layout: post
published: true
title: ! 'HackerGuide: Crack Password Encrypted Zip-files'
permalink: /hackerguide-crack-password-encrypted-zip-files/
wordpress_id: 607
categories:
- News
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
- encrypted password cracker
- crack zip
- enter password for the encrypted file
- crack encrypted password
- how to open encrypted rar files
---


<a href="http://oldhome.schmorp.de/marc/fcrackzip.html">fcrackzip</a> is a zip-file encryption cracker, which can handle (recover / <a href="http://en.wikipedia.org/wiki/Password_cracking">crack</a> / hack) any password encrypted zipfile. Inside it uses a number of methods to accomplish the crack, but this happens nicely behind the scenes.

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
