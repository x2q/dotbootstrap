---
layout: post
published: true
title: Slow Query Log Analyzes Tools
permalink: /slow-query-log-analyzes-tools/
wordpress_id: 668
categories:
- News
- Linux
- Debian
- MySQL
- PHP
- performance
- optimization
- web application
- slow query log analyzer
- mysql slow query log parser
---


From time to time I'm doing some experiments on my server that is hosting this blog. Recently I found out that my blogging software used here, Wordpress, missed some indexes in the MySQL database.

This <a href="http://www.mysqlperformanceblog.com/2006/09/06/slow-query-log-analyzes-tools/">article</a> from <a href="http://www.mysqlperformanceblog.com/">MySQL Performance Blog</a> explains how to log slow queries and how to identify queries, which do not use indexes.

<blockquote>
MySQL has simple but quite handy feature - slow query log, which allows you to log all queries which took over define number of seconds to execute. There is also an option to enable logging queries which do not use indexes even if they take less time (--log-queries-not-using-indexes)

Slow query log is great to spot really slow queries which are often good candidates for optimization but it has few serious problems which limits extent to which it is helpful. First - it only allows you to set slow query time in seconds, having 1 second minimum value. For most of interactive applications this is way too large - if you're developing Web application you probably want whole page to be generated less in 1 second, which issues many queries during generation. Second - if you enable option to log queries which do not use indexes it well can be flooded with fast and efficient queries, which just happen to do full table scans - for example if you would be having drop down list of states in your application and use SELECT * FROM STATES for that it would trigger and log the query.
</blockquote>

