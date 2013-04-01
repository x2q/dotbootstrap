---
layout: post
published: true
title: Howto install Fedora Core 5 (FC5) from a USB-stick
permalink: /howto-install-fedora-core-5-fc5-from-a-usb-stick/
wordpress_id: 234
categories:
- Links
- Linux
- Fedora
- Fedora Core
- usb key device
- install fedora from usb
- install centos from usb
- centos netinstall usb
- centos usb install
- centos install from usb
---


<strong>Download the Fedora disk image from a mirror:</strong>

```

cc@fedora:~$ wget <a title="http://mirrors.dotsrc.org/fedora/5/i386/os/images/diskboot.img" href="http://mirrors.dotsrc.org/">http://mirrors.dotsrc.org/fedora/5/i386/os/images/diskboot.img</a>

```


<strong>Make sure that the USB device is unmounted:</strong>

```

cc@fedora:~$ sudo umount /dev/sda1

```

<strong>Copy the img to the usb key device:</strong>

```

cc@fedora:~$ dd if=diskboot.img of=/dev/sda

```

<strong>Reboot and then select a network based install by typing:</strong>

```

linux askmethod

```



