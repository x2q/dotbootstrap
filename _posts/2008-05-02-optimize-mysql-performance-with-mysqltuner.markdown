---
layout: post
published: true
title: Optimize MySQL Performance With MySQLTuner
permalink: /optimize-mysql-performance-with-mysqltuner/
wordpress_id: 617
categories:
- News
- Linux
- Debian
- Ubuntu
- Fedora
- MySQL
- performance
- PostgreSQL
- MSSQL
- perl
- Major
- General
- Hayden
- RAM
- mysql optimization script
- mysqltuner windows
- mysql optimize script
- optimize mysql
- optimize mysql performance
---



MySQLTuner is a high-performance MySQL tuning script written in perl that will provide you with a snapshot of a MySQL server&acirc;&euro;&trade;s health. Based on the statistics gathered, specific recommendations will be provided that will increase a MySQL server&acirc;&euro;&trade;s efficiency and performance. The script gives you automated MySQL tuning that is on the level of what you would receive from a MySQL DBA.

<strong>I ran this on the server that hosts this blog</strong>

```

# wget http://mysqltuner.com/mysqltuner.pl
# chmod +x mysqltuner.pl
# ./mysqltuner.pl

```



<strong>Result</strong>

```

 >>  MySQLTuner 0.9.0 - Major Hayden <major @mhtx.net>
 >>  Bug reports, feature requests, and downloads at http://mysqltuner.com/
 >>  Run with '--help' for additional options and output filtering
Please enter your MySQL administrative login: secret
Please enter your MySQL administrative password: more secret

-------- General Statistics --------------------------------------------------
[OK] You have the latest version of MySQLTuner
[OK] Currently running supported MySQL version 5.0.32-Debian_7etch4-log
[OK] Operating on 32-bit architecture with less than 2GB RAM

-------- Storage Engine Statistics -------------------------------------------
[--] Status: +Archive -BDB -Federated -InnoDB -ISAM -NDBCluster
[--] Data in MyISAM tables: 71M (Tables: 548)

-------- Performance Metrics -------------------------------------------------
[--] Up for: 109d 22h 8m 1s (69M q [7.283 qps], 1M conn, TX: 3B, RX: 3B)
[--] Reads / Writes: 98% / 2%
[--] Total buffers: 2.6M per thread and 58.0M global
[OK] Maximum possible memory usage: 320.5M (62% of installed RAM)
[OK] Slow queries: 0% (39/69M)
[OK] Highest usage of available connections: 63% (63/100)
[OK] Key buffer size / total MyISAM indexes: 16.0M/65.0K
[OK] Key buffer hit rate: 100.0%
[OK] Query cache efficiency: 80.6%
[!!] Query cache prunes per day: 30287
[OK] Sorts requiring temporary tables: 0%
[!!] Temporary tables created on disk: 59%
[OK] Thread cache hit rate: 99%
[!!] Table cache hit rate: 0%
[OK] Open file limit used: 12%
[OK] Table locks acquired immediately: 99%

-------- Recommendations -----------------------------------------------------
General recommendations:
<ul>

    	<li>Enable the slow query log to troubleshoot bad queries</li>
	<li>When making adjustments, make tmp_table_size/max_heap_table_size equal</li>
	<li>Reduce your SELECT DISTINCT queries without LIMIT clauses</li>
	<li>Increase table_cache gradually to avoid file descriptor limits</li>
</ul>


Variables to adjust:
<ul>
	<li>query_cache_size (> 16M)</li>
    	<li>tmp_table_size (> 32M)</li>
    	<li>max_heap_table_size (> 16M)</li>
    	<li>table_cache (> 64)</li>
</ul>


</major>
```


