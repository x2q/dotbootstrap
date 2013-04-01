---
layout: post
published: true
title: How to do syslog from PHP
permalink: /how-to-do-syslog-from-php/
wordpress_id: 968
categories:
- News
- PHP
- syslog
- rsyslog
---


<strong>Configure (r)syslogd</strong>
<strong>vim /etc/rsyslog.d/99-custom-logging.conf</strong>


```

if $syslogfacility-text == 'local6' and $programname == 'log1' then /var/log/log1.log
if $syslogfacility-text == 'local6' and $programname == 'log1' then ~
if $syslogfacility-text == 'local7' and $programname == 'log2' then /var/log/log2.log
if $syslogfacility-text == 'local7' and $programname == 'log2' then ~

```


<strong>The logging code in PHP</strong>


```

openlog("gateway", LOG_PID|LOG_NDELAY, LOG_LOCAL6);
syslog(LOG_INFO, "Test message");

```


<strong>The logging results</strong>


```

tail -f /var/log/log1.log
May 25 21:23:35 thor log1[4354]: test3

```
