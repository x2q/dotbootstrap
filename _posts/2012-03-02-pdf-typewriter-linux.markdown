---
layout: post
published: true
title: PDF Typewriter for Linux
permalink: /pdf-typewriter-linux/
wordpress_id: 1951
categories:
- Linux
- Open Source
- Howto
- Ubuntu
- pdf
- Adobe
- apt
- software
- install
- printer
- how to
- Import
- Export
- roll
- FAX
---
Well, from time to time you need to fill out a PDF form? Shame on the people and organizations that require such crappy solutions. You could print out the form, roll it into a typewriter, and fill out the form. Now you have to FAX it or scan it back into the computer. However, there is a better way! Just type on top of the PDF form using flpsed then print it out to a printer or export it as another PDF. Here&rsquo;s how to install the software on your Ubuntu desktop:


```
sudo apt-get install flpsed
```


Now from a terminal type (or create a launcher):

flpsed
Click on File/Import PDF.
Open your PDF form.
Click on the form and start typing.
When you are done, click on File/Print or File/Export PDF.
