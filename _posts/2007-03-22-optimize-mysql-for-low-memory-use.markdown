---
layout: post
published: true
title: Optimize MySQL for Low Memory Use
permalink: /optimize-mysql-for-low-memory-use/
wordpress_id: 374
categories:
- News
- Linux
- apache
- Open Source
- MySQL
- databases
- performance
- optimization
- InnoDB
- mysql low memory
- mysql memory optimization
- low memory mysql
- reduce mysql memory usage
- mysql memory limit
---
<img align="right" id="image287" src="http://lh5.ggpht.com/-chyHJqN6-00/UVl9zq_VU7I/AAAAAAAAFnI/H-2MNBUylVw/200px-mysql.svg.png" alt="MySQL Logo" /><a href="http://en.wikipedia.org/wiki/MySQL">MySQL</a> is a light database engine compared to <a href="http://en.wikipedia.org/wiki/Comparison_of_relational_database_management_systems">many of it's rivals</a>, but for some reason the <a href="http://en.wikipedia.org/wiki/Debian">Debian</a> <a href="http://www.mysql.com/">MySQL</a>-server package contains a setup that makes it very heavy and memory consuming. The Debian version of becomes memory consuming because it comes with config file where MySQL's most memory consuming and seldom used storage engine <a href="http://en.wikipedia.org/wiki/Innodb">InnoDB</a> is enable. As result of this the <a href="http://www.mysql.com/">MySQL</a> server instance uses around 100MB of memory while almost idle. 

And here comes the optimization tip. 

Since the <a href="http://en.wikipedia.org/wiki/Innodb">InnoDB storage engine</a> is used very seldom it can be disable in most cases and let the server save almost about 100MB of memory.

To disable to InnoDB storage engine add this to my.cnf (the default <a href="http://www.mysql.com/">MySQL</a> configuration files) in /etc/mysql/

```
skip-innodb
```



More on <a href="http://emergent.urbanpug.com/?p=60">MySQL and Apache optimization</a> and <a href="http://emergent.urbanpug.com/?p=61">here</a>


