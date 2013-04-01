---
layout: post
published: true
title: PHP 5.2 and APC (Alternative PHP Cache) Performance
permalink: /php-52-and-apc-alternative-php-cache-performance/
wordpress_id: 392
categories:
- News
- MySQL
- PHP
- performance
- APC
- caching
- html
- USD
- Server Software
- Zeus Technology Ltd
- Connection Times
- Adam Twiss
- myhost.com Server Port
- php apc windows
- php apc performance
---


<strong>With APC</strong>

```
cc@snox:~$ sudo ab -n 10 http://myhost.com/~cc/
This is ApacheBench, Version 2.0.40-dev < $Revision: 1.146 $> apache-2.0
Copyright 1996 Adam Twiss, Zeus Technology Ltd, http://www.zeustech.net/
Copyright 2006 The Apache Software Foundation, http://www.apache.org/

Benchmarking myhost.com (be patient).....done


Server Software:        Apache
Server Hostname:        myhost.com
Server Port:            80

Document Path:          /~cc/
Document Length:        43525 bytes

Concurrency Level:      1
Time taken for tests:   1.937474 seconds
Complete requests:      10
Failed requests:        0
Write errors:           0
Total transferred:      437420 bytes
HTML transferred:       435250 bytes
Requests per second:    5.16 [#/sec] (mean)
Time per request:       193.747 [ms] (mean)
Time per request:       193.747 [ms] (mean, across all concurrent requests)
Transfer rate:          220.39 [Kbytes/sec] received

Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:        0    0   0.0      0       0
Processing:   192  193   1.3    193     195
Waiting:        0   19  13.7     28      30
Total:        192  193   1.3    193     195

Percentage of the requests served within a certain time (ms)
  50%    193
  66%    193
  75%    195
  80%    195
  90%    195
  95%    195
  98%    195
  99%    195
 100%    195 (longest request)
cc@snox:~$

```




<strong>Without APC</strong>

```

cc@snox:~$ sudo ab -n 10 http://myhost.com/~cc/
This is ApacheBench, Version 2.0.40-dev < $Revision: 1.146 $> apache-2.0
Copyright 1996 Adam Twiss, Zeus Technology Ltd, http://www.zeustech.net/
Copyright 2006 The Apache Software Foundation, http://www.apache.org/

Benchmarking myhost.com (be patient).....done


Server Software:        Apache
Server Hostname:        myhost.com
Server Port:            80

Document Path:          /~cc/
Document Length:        43525 bytes

Concurrency Level:      1
Time taken for tests:   2.842836 seconds
Complete requests:      10
Failed requests:        0
Write errors:           0
Total transferred:      437420 bytes
HTML transferred:       435250 bytes
Requests per second:    3.52 [#/sec] (mean)
Time per request:       284.284 [ms] (mean)
Time per request:       284.284 [ms] (mean, across all concurrent requests)
Transfer rate:          150.20 [Kbytes/sec] received

Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:        0    0   0.0      0       0
Processing:   283  283   1.4    283     286
Waiting:      102  102   0.7    102     104
Total:        283  283   1.4    283     286

Percentage of the requests served within a certain time (ms)
  50%    283
  66%    283
  75%    285
  80%    285
  90%    286
  95%    286
  98%    286
  99%    286
 100%    286 (longest request)

```


<a href="http://www.mysqlperformanceblog.com/2006/08/09/cache-performance-comparison/">More on  APC Cache, Memcached Cache, and MySQL Query Cache performance</a>
