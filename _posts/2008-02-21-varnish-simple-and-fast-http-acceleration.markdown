---
layout: post
published: true
title: ! 'Varnish : Simple and Fast HTTP Acceleration'
permalink: /varnish-simple-and-fast-http-acceleration/
wordpress_id: 597
categories:
- Links
- Linux
- apache
- Open Source
- Debian
- Ubuntu
- Fedora
- FreeBSD
- caching
- http
- html
- USD
- Server Software
- Zeus Technology Ltd
- Connection Times
- Adam Twiss
- Server Port
- varnish apache
- varnish howto
- apache varnish
- varnish ubuntu
- ruby varnish
- ubuntu varnish
- varnish tutorial
---


This article outlines how to cache dynamic content with <a href="https://www.varnish-cache.org/">Varnish HTTP Acceleration</a>.

<a href="https://www.varnish-cache.org/trac/ticket/190">More documentation on dynamic content caching and acceleration</a>.


My own performance benchmark:
<small>

```


cmc@eos:~$ ab -n 50000 http://www.conscius.com/
This is ApacheBench, Version 2.0.40-dev < $Revision: 1.146 $> apache-2.0
Copyright 1996 Adam Twiss, Zeus Technology Ltd, http://www.zeustech.net/
Copyright 2006 The Apache Software Foundation, http://www.apache.org/

Benchmarking www.conscius.com (be patient)
Completed 5000 requests
Completed 10000 requests
Completed 15000 requests
Completed 20000 requests
Completed 25000 requests
Completed 30000 requests
Completed 35000 requests
Completed 40000 requests
Completed 45000 requests
Finished 50000 requests


Server Software:        Apache-Coyote/1.1
Server Hostname:        www.conscius.com
Server Port:            80

Document Path:          /
Document Length:        25038 bytes

Concurrency Level:      1
Time taken for tests:   9.777238 seconds
Complete requests:      50000
Failed requests:        0
Write errors:           0
Total transferred:      1264082781 bytes
HTML transferred:       1251900000 bytes
Requests per second:    5113.92 [#/sec] (mean)
Time per request:       0.196 [ms] (mean)
Time per request:       0.196 [ms] (mean, across all concurrent requests)
Transfer rate:          126258.05 [Kbytes/sec] received

Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:        0    0   0.0      0       0
Processing:     0    0   0.0      0       3
Waiting:        0    0   0.0      0       0
Total:          0    0   0.0      0       3

Percentage of the requests served within a certain time (ms)
  50%      0
  66%      0
  75%      0
  80%      0
  90%      0
  95%      0
  98%      0
  99%      0
 100%      3 (longest request)
cmc@eos:~$


```

</small>
