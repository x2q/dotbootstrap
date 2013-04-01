---
layout: post
published: true
title: ! 'Howto: Resize Xen Loop Disk Image'
permalink: /howto-resize-xen-loop-disk-image/
wordpress_id: 766
categories:
- News
- Linux
- Open Standards
- Design
- Xen
- Debian
- Ubuntu
- Fedora
- FreeBSD
- virtualization
- kvm
- virtualbox
- Qemu
- Win4lin
- ext2
- ext3
- ext4
- filesystem
- image
- virtual server
- Resize xen image
---


<a href="http://en.wikipedia.org/wiki/Win4Lin">Win4lin</a>, <a href="http://en.wikipedia.org/wiki/Kernel-based_Virtual_Machine">KVM</a>, <a href="http://en.wikipedia.org/wiki/QEMU">QEMU</a>, <a href="http://en.wikipedia.org/wiki/Virtualbox">Virtualbox</a> and <a href="http://en.wikipedia.org/wiki/Xen">Xen</a> are all widely used technologies, used in virtual servers. Fairly often a virtual server run from within a loop filesystem and generally start with a fairly small file (1GB is big for a normal file, but not when it is pretending to be an entire filesystem!)

However things often grow over time.

Here is a nice simple procedure for increasing the size of a loop filesystem, if the filesystem is <a href="http://en.wikipedia.org/wiki/Ext2">ext2</a> or <a href="http://en.wikipedia.org/wiki/Ext3">ext3</a> (the procedure should work for <a href="http://en.wikipedia.org/wiki/Ext4">ext4</a> too, but I havn't tested it yet)

<strong>1. Stop the virtual server that is using the loop filesystem</strong>
<strong>2. Add some extra space to your loop filesystem file</strong>

```
# dd if=/dev/zero bs=1024k count=1024 >> loop_image_file
```


This adds 1GB to the end of a file called loop_image_file (make sure to use the append output redirector >> not a single >, otherwise you'll have an empty 1GB file!)

<strong>3. Force a check on the resized/increased filesystem</strong>

```
# e2fsck -f loop_image_file
```


<strong>4. Resize the filesystem within the loop filesystem file</strong>

```
# resize2fs loop_image_file
```


<strong>5. Start the virtual server again</strong>
