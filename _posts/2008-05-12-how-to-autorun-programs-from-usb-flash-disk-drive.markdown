---
layout: post
published: true
title: How To Autorun Programs From USB Flash Disk Drive
permalink: /how-to-autorun-programs-from-usb-flash-disk-drive/
wordpress_id: 618
categories:
- News
- Windows
- xp
- autorun
- powerpoint
- USB
- flashdrive
- Disk Drive
- linux autorun usb
- ubuntu autorun usb
- linux usb autorun
- autorun flash disk
- autorun usb mac
- autorun usb linux
---



The autorun mechanism was introduced for CDs back in the 90s and was used to automatically run programs and applications when the CD was inserted. This autorun feature has also made its way to USB flash disk drives.

The following is a guideline on how to create an autorun-usb drive. 

<strong>1.</strong> Create a plain text file in the root of the USB drive (eg. G:\) and name it <strong>autorun.inf</strong>.
<strong>2.</strong> Open Notepad the <strong>autorun.inf</strong> file in notepad

<strong>3.</strong> Type in:

```

[autorun]
open=start.exe
action=Run My Program
icon=start.exe
label=My Program

```


<strong>4.</strong> Save the file


The start.exe-file should be opened when the USB drive is inserted into a PC.


The autorun-function can also be used to open PowerPoint presentations and any other file types automatically when inserted into a machine.

Type this into the autorun.inf to run a PowerPoint presentation named <strong>my.ppt</strong>.

```

[autorun]
open=<strong>my.ppt</strong>
action=<strong>Open my.ppt</strong>

```

 
