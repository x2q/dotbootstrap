---
layout: post
published: true
title: Importing / Exporting Virtual Disk Images with Virtual Box
permalink: /importing-exporting-virtual-disk-images-with-virtual-box/
wordpress_id: 653
categories:
- News
- Sun
- VMware
- virtualbox
- Virtual Machine
- Manager
- virtualbox export virtual machine
- VBoxManage export
- virtualbox export
- VirtualBox import Virtual PC
- virtualbox export machine
- export virtualbox machine
---


<a href="https://blogs.oracle.com/roller-ui/errors/404.jsp">Importing / Exporting Virtual Disk Images with Virtual Box : Prosthetic Conscious</a><br /><blockquote>Importing / Exporting Virtual Disk Images with Virtual Box<br /><br />Virtual Box is amazing for an open source project. It comes close to VMWare in usability. Where it falls short is importing and exporting images. There's no support in the user interface for this. If you feel comfortable using the command line, you can export and import a disk image. Here's how,<br /><br />To export:<br /><br />   1. Shut down the VM<br />   2. Use the "VBoxManager clonevdi ..." CLI to copy the disk image. On my Mac this was at /usr/bin/vboxmanage<br /><br />To import:<br /><br />   1. Register the disk image: File>Virtual Disk Manager>Add<br />   2. Create a new VM, and use the disk image you added in step 1<br /><br />The obvious problem is that the .vdi file is just a disk image. It doesn't capture the virtual machine. You must know the correct parameters to use when you create the VM in the import process or the disk image won't be able to run. It also doesn't capture the state of the virtual machine. <br /><br />Vbox has a very nice snapshot feature. If one could import / export snapshots it would be perfect.</blockquote>
