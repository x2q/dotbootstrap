---
layout: post
published: true
title: ! 'MySQL: Remove Duplicate Entries'
permalink: /mysql-remove-duplicate-entries/
wordpress_id: 388
categories:
- Links
- Linux
- MySQL
- mysql remove duplicates
- mysql delete duplicates
- mysql remove duplicate rows
- mysql delete duplicate rows
- remove duplicates mysql
- UNIQUE
---


Remove duplicate entries is fairly hardcore, if the identify and delete approach is used - an approach described in detail <a href="http://www.xaprb.com/blog/2006/10/09/how-to-find-duplicate-rows-with-sql/">here</a>. An other approach to the problem of duplicates is to simply add a UNIQUE index to the current table and thereby let MySQL do the hardcore identification and deletion job.

<strong>Short example of the index approach</strong>.

Assume the following table and data
<code lang="SQL">
CREATE TABLE myDATA (
id int(10) NOT NULL auto_increment,
a int,
b int,
c int,
updated timestamp(14),
PRIMARY KEY (id)
);

insert into myData (a,b,c) values (1,2,3);
insert into myData (a,b,c) values (1,2,3);
insert into myData (a,b,c) values (1,5,4);
insert into myData (a,b,c) values (1,6,4);

```



<code lang="SQL">
mysql> select * from dupTest;
select * from dupTest;
+------+------+------+------+---------------------+
| pkey | a | b | c | timeEnter |
+------+------+------+------+---------------------+
| 1 | 1 | 2 | 3 | 2004-04-16 10:55:35 |
| 2 | 1 | 2 | 3 | 2004-04-16 10:55:35 |
| 3 | 1 | 5 | 4 | 2004-04-16 10:55:35 |
| 4 | 1 | 6 | 4 | 2004-04-16 10:55:35 |
+------+------+------+------+---------------------+
4 rows in set (0.00 sec)

```



mysql>

Note, the first two rows contains duplicates in columns a and b. It contains
other duplicates; but, leaves the other duplicates alone.

mysql> ALTER IGNORE TABLE dupTest ADD UNIQUE INDEX(a,b);

mysql> select * from dupTest;
select * from dupTest;
+------+------+------+------+---------------------+
| pkey | a | b | c | timeEnter |
+------+------+------+------+---------------------+
| 1 | 1 | 2 | 3 | 2004-04-16 11:11:42 |
| 3 | 1 | 5 | 4 | 2004-04-16 11:11:42 |
| 4 | 1 | 6 | 4 | 2004-04-16 11:11:42 |
+------+------+------+------+---------------------+
3 rows in set (0.00 sec) 
