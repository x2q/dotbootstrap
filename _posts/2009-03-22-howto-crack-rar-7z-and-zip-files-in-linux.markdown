---
layout: post
published: true
title: Howto Crack Rar, 7z, and zip files in Linux
permalink: /howto-crack-rar-7z-and-zip-files-in-linux/
wordpress_id: 761
categories:
- News
- Linux
- Crack
- hack
- encryption
- password
- 7z
- rar
- unrar
- zip
- brute-force
- brute-force algorithm
- crack rar password mac
- crack rar password
- crack rar password linux
- how to crack rar password
- rar password cracker linux
---


If you forget your password for compressed archive (rar, 7z, zip), <a href="http://rarcrack.sourceforge.net/">RarCrack</a> is the solution. <a href="http://rarcrack.sourceforge.net/">RarCrack</a> uses a brute-force algorithm to find correct password. You can specify which characters will be used in password generations.

<strong>Preparing your system for installation</strong>

Install the following package
# aptitude install libxml2-dev build-essential


Download the latest version of rarcrack from here
# wget http://surfnet.dl.sourceforge.net/sourceforge/rarcrack/rarcrack-0.2.tar.bz2

Extract the tarball file

#tar xvjf rarcrack-0.2.tar.bz2

#cd rarcrack-0.2

#make

#make install

<strong>Using Rarcrack</strong>

rarcrack your_encrypted_archive.ext [--threads thread_num] [--type rar|zip|7z]

Example with a rar-file, 7z-file, and zip-file
# rarcrack password_protected.rar
# rarcrack password_protected.7z
# rarcrack password_protected.zip
