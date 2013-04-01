---
layout: post
published: true
title: Installing Xen on Debian Etch 4.0
permalink: /installing-xen-on-debian-etch-40/
wordpress_id: 318
categories:
- News
- Linux
- Open Source
- Xen
- Debian
- Ubuntu
- Fedora
- Microsoft
- virtualization
- VMware
- performance
- Virtual Machine
- virtual machine creator
- collection package containing different tools
- debian xen
- xen debian
- installing xen on debian
- install xen on debian
- install xen debian
---
<strong>Updated 15. August 2007</strong>



<img align="right" style="background-color: #FFF;" id="image266" src="http://lh4.ggpht.com/-RPrBqOQTWrc/UVl9ipKAHXI/AAAAAAAAFlQ/sMsiwuC7tAg/xenlogo.png" alt="Xen Logo" />For a long time I have tested many different virtualization techniques; <a href="http://en.wikipedia.org/wiki/Xen">Xen</a>, <a href="http://en.wikipedia.org/wiki/Vmware">VMWare</a>, and Microsoft VM. Until now I'm able to conclude that all of them are usable on my desktop machine, but both <a href="http://en.wikipedia.org/wiki/Vmware">VMWare</a> and Microsoft's VM are more sluggish that <a href="http://en.wikipedia.org/wiki/Xen">Xen</a>. This weekend I deployed my first server based on the upcoming <a href="http://en.wikipedia.org/wiki/Debian">Debian</a> <a href="http://en.wikipedia.org/wiki/Etch_%28Debian%29">Etch</a> and <a href="http://en.wikipedia.org/wiki/Xen">Xen</a>. Everything worked out of the box.

Here is what I did to install <a href="http://en.wikipedia.org/wiki/Xen">Xen</a> on <a href="http://en.wikipedia.org/wiki/Debian">Debian</a> Etch:

```

sudo apt-get install xen-linux-system-2.6.18-4-xen-686 libc6-xen bridge-utils

```



Boot into the newly installed Xen enabled Linux kernel

```

sudo reboot

```


Then adjusted the network settings in /etc/xen/xend-config.sxp. Enabling the network bridge:

```

(network-script network-bridge)

```




Install xen-tools:

```

apt-get install xen-tools

```

Xen tools is a collection package containing different tools related to Xen, a virtual machine creator etc.

Edit adjust the kernel and initrd parameters in /etc/xen-tools/xen-tools.conf to match the ones on your system:

Find out what the kernel image and initrd is named by:

```

ls /boot/vmlinuz*
/boot/vmlinuz-2.6.18-4-686  /boot/vmlinuz-2.6.18-4-xen-686

```


and

ls /boot/initrd*
/boot/initrd.img-2.6.18-4-686  /boot/initrd.img-2.6.18-4-686.bak  /boot/initrd.img-2.6.18-4-xen-686

Adjust the lines

```

#
# Default kernel and ramdisk to use for the virtual servers
#
kernel = /boot/vmlinuz-2.6.18-4-xen-686
initrd = /boot/initrd.img-2.6.18-4-xen-686

```



Further adjust the xen-tools.conf to this settings:

```

dir = /home/xen
debootstrap = 1
size   = 4Gb      # Disk image size.
memory = 128Mb    # Memory size
swap   = 128Mb    # Swap size
fs     = ext3     # use the EXT3 filesystem for the disk image.
dist   = etch    # Default distribution to install.
image  = sparse   # Specify sparse vs. full disk images.

```


Create a home for all the coming virtual Xen guests:

```

mkdir /home/xen
mkdir /home/xen/domains

```




And then ready to create a virtual machine - guest, simply by:

```

xen-create-image -hostname=mailserver -ip=10.0.0.21 -netmask=255.255.255.0 -gateway=10.0.0.1 -passwd

```


Afterwards I was able to fire up the newly created virtual machine with:

```

xm create mailserver.cfg

```


If an error like this shows up

```

Error: Device 0 (vif) could not be connected. Backend device not found.

```

You should check your that you have enabled the network bridge, "(network-script network-bridge)", in /etc/xen/xend-config.sxp and restarted the xen deamon by /etc/init.d/xend restart


When up and running either "xm list" or "xentop" can be used to get an overview of what instance are currently running

```


```

debian5:# sudo xm list
Name                                      ID Mem(MiB) VCPUs State   Time(s)
Domain-0                                   0      874     1 r-----    657.9
mailserver                                 3      128     1 -b----      8.0

```


```



Based on my experiences so far with virtualization and deploying virtualization in a enterprise setup, I really think that <a href="http://en.wikipedia.org/wiki/Xen">Xen</a> is a very strong asset for Linux and Linux based distributions to show the world what they are up to. Virtualization is really a technique for enterprise server and data center managers to make a more robust and simplified setup, and I think that virtualization could play a significant role within the server market the coming years.


