---
layout: post
published: true
title: ! 'Howto: How to Reset the MySQL Root Password'
permalink: /howto-how-to-reset-the-mysql-root-password/
wordpress_id: 933
categories:
- News
- Linux
- Debian
- Ubuntu
- MySQL
- howto
- unix
- password
- reset
---


The following procedure can be used to reset the password for any MySQL root accounts on Linux and Unix (*nix). The instructions assume that you have got the proper permissions on the host system.

<strong>Stop the MySQL daemon process</strong>

```

sudo /etc/init.d/mysql stop

```
 

<strong>Create a text file <em>/home/me/mysql.sql</em> and place the following statements in it. Replace the password with the password that you want to use</strong>

```

UPDATE mysql.user SET Password=PASSWORD('a_new_password') WHERE User='root';
FLUSH PRIVILEGES;

```


The UPDATE and FLUSH statements each must be written on a single line. The UPDATE statement resets the password for all existing root  accounts, and the FLUSH  statement tells the server to reload the grant tables into memory. 

<strong>Start the MySQL server with the special --init-file option</strong>

```

mysqld_safe --init-file=/home/me/mysql.sql

```


Press Ctrl+C and then start the MySQL server again by <strong>/etc/init.d/mysql start</strong> and you are done.
