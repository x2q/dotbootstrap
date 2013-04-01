---
layout: post
published: true
title: How to do MySQL replication (dual-master / multi-master)
permalink: /howto-do-mysql-replication-dual-master-multi-master/
wordpress_id: 262
categories:
- Links
- Linux
- MySQL
- mysql dual master
- mysql dual master replication
---

```

# Mysql node a
[mysqld]
server-id = 10
auto_increment_increment = 10
auto_increment_offset = 1
master-host = nodeb
master-user = replication
master-password = replication

# Mysql node b
[mysqld]
server-id = 20
auto_increment_increment = 10
auto_increment_offset = 2
master-host = nodea
master-user = replication
master-password = replication

```



