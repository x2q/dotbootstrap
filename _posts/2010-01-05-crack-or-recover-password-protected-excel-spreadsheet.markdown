---
layout: post
published: true
title: Crack or Recover Password Protected Excel Spreadsheet
permalink: /crack-or-recover-password-protected-excel-spreadsheet/
wordpress_id: 905
categories:
- News
- Linux
- Ubuntu
- Crack
- Microsoft
- Excel
- hack
- office
- doc
- recover
- password
- xls
- xlcrack
---


From time to time someone sends me password protected Microsoft Excel (xls-files) spreadsheets. Getting xls files is in it self is bothersome, but that&rsquo;s the way the world of IT is today, but hopefully more and more home and business users discover the <a href="http://www.openoffice.org/">OpenOffice productivity suite</a> in the future. But getting password protected xls-files is just incredibly annoying &ndash; first of all it tells you that the person that just sent you the spreadsheet doesn&rsquo;t have a clue on security matters, since protection techniques of that type is of no real use. They are simply too easy to crack, but again &ndash; why at all protect a document&hellip;

<strong>Howto Crack And Get Rid Of The "Password Protection" / "Recover" The Spreadsheet on Ubuntu</strong>

In order to perform the crack / recovery, we are going to use a small utility called xlcrack, xlcrack recovers lost or forgotten passwords from XLS files such as those created by Microsoft Excel. Some newer XLS files are not suitable for password recovery using this software.

<strong>Install libgsf-1</strong>

```

sudo aptitude install libgsf-1-dev

```


<strong>Download and compile xlcrack</strong>

```

wget http://freshmeat.net/urls/1d5772c1c5bea2854e1d04b29f1f772a
tar zxvf xlcrack-1.2.tar.gz
cd xlcrack-1.2
make

```




<strong>Crack / Recover A Password From a XLS-file</strong>

```

./xlcrack password_protected_spreadsheet.xls
password_protected_spreadsheet.xls: 1234

```
