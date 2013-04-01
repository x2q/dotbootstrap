---
layout: post
published: true
title: How to mount bin / cue image files in Linux
permalink: /how-to-mount-bin-cue-image-files-in-linux/
wordpress_id: 844
categories:
- News
- Linux
- Debian
- Ubuntu
- Fedora
- iso
- unix
- filesystem
- bin/cue
- mount
- mount bin ubuntu
- ubuntu mount bin
- straight forward
- quite straight forward
- crap windows software
---


Mounting iso-files in Linux is quite straight forward and simple e.g. using the mounter function in Ubuntu straight from the context menu or by using a command line like this: mount -o loop image.iso /mnt.

Anyway mounting bin/cue image files is not that straight forward as they'll need conversion to iso before mounting, however the process is quite simple, but it need a small application called bchunk. The bchunk package contains a UNIX/C rewrite of the BinChunker program. BinChunker converts a CD image in a .bin/.cue format (sometimes .raw/.cue) into a set of .iso and .cdr/.wav tracks. The .bin/.cue format is used by some non-UNIX CD-writing software (read crap windows software), but is not supported on most other CD-writing programs.

$ sudo aptitude install bchunk

In order to convert a bin/cue image set:

$ bchunk image.bin image.cue image.iso

Then to mount the iso image using this command:
mount -o loop image.iso /mnt
