---
layout: post
published: true
title: Combine Multiple PDFs Into One File
permalink: /combine-multiple-pdfs-into-one-file/
wordpress_id: 962
categories:
- News
- Linux
- Debian
- Ubuntu
- pdf
- combine
- Ghostscript
- pdftk
---


From time to time it is very useful to combine multiple PDF documents into one file. 

Install gs (ghostscript) and pdftk (tool for manipulating PDF documents)

```

sudo aptitude install gs pdftk

```


Now we will see one example, which shows how to combine a few pdf files; 1.pdf,2.pdf,3.pdf.

```

gs -dNOPAUSE -sDEVICE=pdfwrite -sOUTPUTFILE=combined_pdf.pdf -dBATCH 1.pdf 2.pdf 3.pdf

```


If you want to know more options available for gs command check the <a href="http://linux.die.net/man/1/gs">gs man page</a>
