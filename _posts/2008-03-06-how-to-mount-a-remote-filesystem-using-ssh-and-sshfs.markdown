---
layout: post
published: true
title: How to Mount a Remote Filesystem Using SSH and sshfs
permalink: /how-to-mount-a-remote-filesystem-using-ssh-and-sshfs/
wordpress_id: 602
categories:
- News
- Linux
- Open Source
- Debian
- Ubuntu
- Fedora
- Microsoft
- FreeBSD
- SSH
- NetBSD
- OpenBSD
- ! '*nix'
- cc /media/mountpoint
- sshfs windows 7
- freebsd mount ssh
- mount sshfs
- sshfs windows xp
- mount ssh windows
---


From time to time I work on remote servers and some times it would be very useful to be able to mount the remote file system on my local machine. Recently I found sshfs, which is a filesystem client based on the <a href="http://en.wikipedia.org/wiki/Secure_Shell">SSH</a> File Transfer Protocol and since most <a href="http://en.wikipedia.org/wiki/Unix-like">*nix</a> like servers; <a href="http://en.wikipedia.org/wiki/Linux">Linux</a>, <a href="http://en.wikipedia.org/wiki/Freebsd">FreeBSD</a>, <a href="http://en.wikipedia.org/wiki/NetBSD">NetBSD</a>, <a href="http://en.wikipedia.org/wiki/Openbsd">OpenBSD</a> servers with <a href="http://en.wikipedia.org/wiki/OpenSSH">OpenSSH</a> installed already support this protocol it is very easy to set up - Read: on the server side there's nothing to do, setup or configure. On the client side mounting the filesystem is as easy as logging into the server with <a href="http://en.wikipedia.org/wiki/Secure_Shell">SSH</a>.

Technically (more) the sshfs is based on <a href="http://en.wikipedia.org/wiki/Filesystem_in_Userspace">FUSE</a>, which is the best <a href="http://en.wikipedia.org/wiki/Filesystem_in_Userspace">userspace filesystem framework for linux</a> ;-)

Here is how I connect to my remote <a href="http://en.wikipedia.org/wiki/Secure_Shell">SSH</a>-based servers and hosts:


```

$ sshfs -o uid=1000,gid=1000 cc@remote.host.com:/home/cc /media/mountpoint

```


I use the uid and gid arguments to give my own normal user with those uid and gid to have write access to the mounted filesystem.




This <a href="http://embraceubuntu.com/2005/10/28/how-to-mount-a-remote-ssh-filesystem-using-sshfs/">post</a> describes the sshfs in more details and moreover howto use it on Ubuntu and Debian.

<a href="http://fuse.sourceforge.net/sshfs.html">The sshfs website.</a>
