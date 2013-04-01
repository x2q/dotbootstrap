---
layout: post
published: true
title: Brother MFC-7440N PPD Linux CUPS/LPR Driver
permalink: /brother-mfc-7440n-ppd-linux-cupslpr-driver/
wordpress_id: 2003
categories:
- Linux
- Open Source
- Howto
- Ubuntu
- brother
- driver
- MFC
- MFC-7440N
- Cups
- LPR
---


I've spent more or less a whole day to find a way to install a <a href="http://www.brother-usa.com/MFC/ModelDetail/4/MFC7440N/Overview">Brother MFC-7440 Printer</a> on <a href="http://www.ubuntu.com/">Ubuntu 12.04</a>, unfortunately there is no ppd file for the model. Download the <a href="https://www.dropbox.com/s/fti09lo9kykwt25/MFC7440N.ppd">MFC7440N.ppd</a>.

I followed the steps on Brother web site:

```
cc@ea:~/Downloads$ sudo dpkg -D20000 -i cupswrapperMFC7440N-2.0.2-1.i386.deb 
(Reading database ... 266549 files and directories currently installed.)
Preparing to replace cupswrappermfc7440n:i386 2.0.2-1 (using cupswrapperMFC7440N-2.0.2-1.i386.deb) ...
D020000: trigproc_activate_packageprocessing pkg=cupswrappermfc7440n:i386
cups stop/waiting
cups start/running, process 14167
D020000: post_script_tasks - ensure_diversions; trig_incorporate
Unpacking replacement cupswrappermfc7440n:i386 ...
D020000: post_script_tasks - ensure_diversions; trig_incorporate
Setting up cupswrappermfc7440n:i386 (2.0.2-1) ...
D020000: trigproc_activate_packageprocessing pkg=cupswrappermfc7440n:i386
ERROR : Brother LPD filter is not installed.
chmod: cannot access `/usr/local/Brother/inf/brMFC7440Nrc': No such file or directory
chmod: cannot access `/usr/local/Brother/inf': No such file or directory
cups stop/waiting
cups start/running, process 14218
D020000: post_postinst_tasks_core - trig_incorporate

```


It turned out that the LPR needed to be installed before the Cups Wrapper.

```
wget https://www.dropbox.com/s/0hu9v5iaa03o71z/brmfc7440nlpr-2.0.2-1.i386.deb
wget https://www.dropbox.com/s/5barvktvrhle2qj/cupswrapperMFC7440N-2.0.2-1.i386.deb
cc@ea:~/Downloads$ sudo dpkg -i brmfc7440nlpr-2.0.2-1.i386.deb
cc@ea:~/Downloads$ sudo dpkg -i cupswrapperMFC7440N-2.0.2-1.i386.deb 
```


You can fetch the PPD file directly from <a href="https://www.dropbox.com/s/fti09lo9kykwt25/MFC7440N.ppd">https://www.dropbox.com/s/fti09lo9kykwt25/MFC7440N.ppd</a>.
