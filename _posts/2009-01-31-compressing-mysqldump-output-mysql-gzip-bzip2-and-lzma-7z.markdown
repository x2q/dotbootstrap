---
layout: post
published: true
title: Compressing mysqldump output - mysql, gzip, bzip2 and LZMA (7z)
permalink: /compressing-mysqldump-output-mysql-gzip-bzip2-and-lzma-7z/
wordpress_id: 720
categories:
- News
- Linux
- MySQL
- gzip
- bzip2
- 7z
- mysqldump
- lzma
- mysqldump gzip
- mysqldump zip
- mysqldump compress
- mysqldump bzip
- mysqldump bzip2
---


<strong>Do a mysql dump and compress directly with gzip</strong>
mysqldump < mysqldump options> | gzip > outputfile.sql.gz

<strong>Gunzip and import using gzip</strong>
gunzip < outputfile.sql.gz | mysql < mysql options> 


<strong>Do a mysql dump and compress directly with bzip2</strong>
mysqldump < mysqldump options> | bzip2 > outputfile.sql.bz2

<strong>Bunzip2 and import using bzip2</strong>
bunzip2 < outputfile.sql.bz2 | mysql < mysql options> 


<strong>Do a mysql dump and compress directly with lzma</strong>
mysqldump < mysqldump options> | lzma > outputfile.sql.lzma

<strong>Unlzma and import using unlzma</strong>
unlzma < outputfile.sql.lzma | mysql < mysql options> 
