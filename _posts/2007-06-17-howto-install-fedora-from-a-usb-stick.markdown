---
layout: post
published: true
title: Howto Install Fedora From a USB Flash Key Drive
permalink: /howto-install-fedora-from-a-usb-stick/
wordpress_id: 428
categories:
- Links
- News
- Linux
- Ubuntu
- Fedora
- http
- OpenSUSE
- usb key device
- Fedora 7
- install fedora from usb
- fedora usb install
- fedora 11 netinst
- install fedora 11 from usb
- fedora 11 netinstall
---


<img align="right" id="image427" src="http://lh5.ggpht.com/-hJ1QlqlPlYc/UVl-COI3LII/AAAAAAAAFoo/ts8h5eU0xDo/fedora-logo.png" alt="Fedora Logo" />From time to time it is comfortable to be able to install software from USB devices; keys and sticks rather than burning CDs and DVDs and the like for installation.

Outlined here below are the essential commands for preparing an USB memory key with <a href="http://fedoraproject.org/">Fedora 7</a> installation image.

Here is the bug report. Please provide feedback if you can.

<strong>Download the <a href="http://fedoraproject.org/">Fedora</a> disk image from a mirror:</strong>

```

cc@fedora:~$ wget <a title="http://ftp.tu-chemnitz.de/pub/linux/fedora-enchilada/linux/releases/7/Fedora/i386/os/images/diskboot.img" href="http://ftp.tu-chemnitz.de/pub/linux/">http://ftp.tu-chemnitz.de/pub/linux/fedora-enchilada/linux/releases/7/Fedora/i386/os/images/diskboot.img</a>

```


<strong>Copy the bootdisk image to the USB device:</strong>
<strong>Be aware</strong> to choose the right device before transferring the bootdisk image. Ensure by either mount and unmount the USB key device before doing the operation or check the contents of the device. Make sure that the USB device is unmounted before transferring.

```

cc@fedora:~$ sudo umount /dev/sda1

```

<strong>Copy the img to the usb key device:</strong>

```

cc@fedora:~$ dd if=diskboot.img of=/dev/sda

```


<strong>Reboot and start a network based install</strong>
When you reboot you&acirc;&euro;&trade;ll be able to choose network installation. Both HTTP-based and FTP-based install are available. I prefer HTTP-based install, since they seem to work smother than the FTP-based. Before the actual installation takes place you are asked to provided a URL of a Fedora mirror, from where the installation can fetch required packages etc. Help yourself by writing down a URL before rebooting.

```

linux askmethod

```


Feel free to comment. Please report if this method is useful for <a href="http://www.debian.org/">Debian</a>, <a href="http://www.ubuntu.com/">Ubuntu</a> or <a href="http://en.opensuse.org/Main_Page">OpenSUSE</a> installations too.


