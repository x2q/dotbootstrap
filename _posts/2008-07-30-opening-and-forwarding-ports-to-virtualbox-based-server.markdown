---
layout: post
published: true
title: Opening and Forwarding Ports To A VirtualBox-based Guest
permalink: /opening-and-forwarding-ports-to-virtualbox-based-server/
wordpress_id: 654
categories:
- News
- apache
- MySQL
- SSH
- PostgreSQL
- http
- virtualbox
- forwarding
- httpd
- SSH Server Port
- virtualbox port forwarding
- virtualbox open port
- virtualbox open ports
- virtualbox port forward
- virtualbox port forwarding windows
---


Here are the commands used to open and forward the host's port 2222 to the guest's port 22 (SSH Server Port).

<strong>Type this into a terminal:</strong>



```

VBoxManage setextradata nameofyourguest "VBoxInternal/Devices/pcnet/0/LUN#0/Config/postgresql/HostPort" 5432
VBoxManage setextradata nameofyourguest "VBoxInternal/Devices/pcnet/0/LUN#0/Config/postgresql/GuestPort" 5432
VBoxManage setextradata nameofyourguest "VBoxInternal/Devices/pcnet/0/LUN#0/Config/postgresql/Protocol" TCP
VBoxManage setextradata nameofyourguest "VBoxInternal/Devices/pcnet/0/LUN#0/Config/http/HostPort" 8080
VBoxManage setextradata nameofyourguest "VBoxInternal/Devices/pcnet/0/LUN#0/Config/http/GuestPort" 80
VBoxManage setextradata nameofyourguest "VBoxInternal/Devices/pcnet/0/LUN#0/Config/http/Protocol" TCP

```



