---
layout: post
published: true
title: ! 'Ubuntu: Print to PDF or PDF Export'
permalink: /ubuntu-print-to-pdf-or-pdf-export/
wordpress_id: 543
categories:
- Links
- Linux
- Usability
- Open Standards
- Open Source
- Debian
- Ubuntu
- Fedora
- user experience
- pdf
- Microsoft Windows
- driver
- Printer Driver
- printing service
- pdf creator ubuntu
- ubuntu print to pdf
- ubuntu pdf creator
- pdf creator for ubuntu
- pdfcreator ubuntu
---


Creating <a href="http://en.wikipedia.org/wiki/Pdf">PDF</a>-files from almost any application under <a href="http://en.wikipedia.org/wiki/Windows">Windows</a> is easy using <a href="http://sourceforge.net/projects/pdfcreator/">PDFCreator</a>. <a href="http://sourceforge.net/projects/pdfcreator/">PDFCreator</a> provide a printer driver, which is exposed to the user as any other printer, so the user use it like a printer in <a href="http://en.wikipedia.org/wiki/Microsoft_Word">Word</a>, <a href="http://en.wikipedia.org/wiki/Microsoft_Excel">Excel</a> or any other <a href="http://en.wikipedia.org/wiki/Windows">Windows application</a>.

For <a href="http://en.wikipedia.org/wiki/Linux">Linux</a> or <a href="http://www.ubuntu.com/">Ubuntu Linux</a> cups-pdf provides the same functionality.

Install it easily using this:

```

$sudo aptitude install cups-pdf

```


Restart your printing service (<a href="http://en.wikipedia.org/wiki/Common_Unix_Printing_System">CUPS</a>) using:

```

$sudo /etc/init.d/cupsys restart

```


Then you should be able to add a new printer (System->Administration->Printing) selecting the &acirc;&euro;&oelig;Local Printer&acirc;&euro; &acirc;&euro;&oelig;PDF Printer&acirc;&euro; option. In the next step choose &acirc;&euro;&oelig;Generic Printer&acirc;&euro; and then used the &acirc;&euro;&oelig;Postscript Color Printer (Ver 3)&acirc;&euro; driver.

Newly setup printer should now be able to print <a href="http://en.wikipedia.org/wiki/Pdf">pdf-files</a>.


Thanks to this post:
http://ubuntu.wordpress.com/2006/03/23/print-to-pdf-using-cups-pdf/

