---
layout: post
published: true
title: Executing SQL Statements from a Text File
permalink: /executing-sql-statements-from-a-text-file/
wordpress_id: 422
categories:
- Links
- Linux
- MySQL
- sql
- Executing SQL Statements from a Text File
---


The mysql client typically is used interactively, like this:


```
debian1:~# mysql db_name
```


However, it is also possible to put your SQL statements in a file and then tell mysql to read its input from that file. To do so, create a text file text_file that contains the statements you wish to execute. Then invoke mysql as shown here:


```
debian1:~# mysql db_name < text_file
```


If you place a USE db_name statement as the first statement in the file, it is unnecessary to specify the database name on the command line:


```

```
debian1:~# mysql < text_file
```


From the <a href="http://dev.mysql.com/doc/refman/5.0/en/batch-commands.html">MySQL Manual</a>

```
