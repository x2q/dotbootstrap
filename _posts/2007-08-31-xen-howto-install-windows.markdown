---
layout: post
published: true
title: ! 'Xen Howto: Install Windows'
permalink: /xen-howto-install-windows/
wordpress_id: 501
categories:
- Links
- Linux
- Open Standards
- Open Source
- Xen
- Vista
- Debian
- Ubuntu
- Fedora
- Microsoft
- Windows
- Intel
- virtualization
- xp
- VNC
- xen-tools
- AMD
- Windows XP
- Windows 2003 Server
- Microsoft Windows
- Virtual Machine
- xen windows
- xen howto
- hvm is required for this operation
- xen install windows
- install windows on xen
- debian xen windows
---



<img align="right" style="background-color: #FFF;" id="image266" src="http://lh3.ggpht.com/-BENOkfI0964/UVl_MQRMhAI/AAAAAAAAFug/7gc4mDufXtc/xenlogo.png" alt="Xen Logo" />
This short guide describes how to install Windows XP or Windows 2003 Server on <a href="http://en.wikipedia.org/wiki/Xen">Xen</a>. It provides an overview of the <a href="http://en.wikipedia.org/wiki/Debian_etch">Debian Linux Etch</a> installation, and detailed steps for installing and configuring <a href="http://en.wikipedia.org/wiki/Xen">Xen</a> and starting the Windows XP or Windows 2003 Server 
installation.


<strong>Requirements</strong>
<ul>
<li>CPU with either Intel's Vanderpool  (<a href="http://en.wikipedia.org/wiki/Vanderpool#Intel_VT_.28IVT.29">IVT - Intel Virtualization Technology</a>) or <a href="http://en.wikipedia.org/wiki/Pacifica_%28virtual_machine%29">AMD's Pacifica Technology (AMD virtualization)</a>
</li>	
<li>Windows iso-image</li>
</ul>


First you need to install <a href="http://en.wikipedia.org/wiki/Xen">Xen</a> on <a href="http://en.wikipedia.org/wiki/Debian">Debian</a> Etch:

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





Install Xen IO Emulation tools:

```

sudo apt-get install xen-ioemu-3.0.3-1

```


Create a directory for the virtual machine files e.g. /home/xen/domains/win01 and create a disk image for the virtual machine's primary disk.

```

mkdir /home/xen
mkdir /home/xen/domains
mkdir /home/xen/domains/win01
sudo dd if=/dev/zero of= /home/xen/domains/win01/disk.img bs=1M count=4096

```


Establish a Xen machine Configuration file (/etc/xen/win01.cfg) like this

```

kernel  = '/usr/lib/xen/boot/hvmloader'
builder = 'hvm'
memory  = '256'
device_model='/usr/lib/xen/bin/qemu-dm'

# Disks
disk    = [ 'file:/home/xen/domains/win01/disk.img,ioemu:hda,w',
            'file:/home/cc/iso-images/WindowsXP-SP2/image.iso,ioemu:hdc:cdrom,r' ]

# Hostname
name    = 'win01'

#  Networking
vif = ['type=ioemu, bridge=xenbr0']

# Behaviour
boot='d'
vnc=1
vncviewer=1
sdl=0

```


The ready to fire up the new machine and start the Windows installation in a vnc terminal.

```

xm create win01.cfg

```



After the virtual machine is started - a VNC server port should be available on port 5900 at the Xen server's IP, e.g. 192.168.1.102 - A VNC XEN Client session is depicted here.

<a class="imagelink" href="http://lh4.ggpht.com/-Si7pJ9PVRh4/UVl_PS2FFPI/AAAAAAAAFuw/yOTZ13knhdc/windows-install-start-on-xen-via-vnc.png" title="Xen Windows Install VNC"><img id="image421" src="http://lh3.ggpht.com/-MLSqipAVVfw/UVl_N4aqwFI/AAAAAAAAFuo/3nx8_nnNQCI/windows-install-start-on-xen-via-vnc.thumbnail.png" alt="Xen Windows Install VNC" /></a>

If an error like this shows up

```

Error: Device 0 (vif) could not be connected. Backend device not found.

```

You should check your that you have enabled the network bridge, "(network-script network-bridge)", in /etc/xen/xend-config.sxp and restarted the xen deamon by /etc/init.d/xend restart


For more on creating Xen virtual machines read <a href="http://www.debian-administration.org/articles/533">this guide</a>, which outlines the features of the xen-tools package.





