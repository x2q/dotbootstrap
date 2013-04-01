---
layout: post
published: true
title: Block referer spam easily
permalink: /block-referer-spam/
wordpress_id: 152
categories:
- News
- Linux
- http
- html
- Web Server
- firewall
- Reading
- apache block referrer
---
<img align='right' src='http://lh4.ggpht.com/-0eohQ3uELyE/UVl8qLfWDJI/AAAAAAAAFfE/kQXiM-1oVH0/illustration.png' alt='ModSecurity' />

I have built this small tutorial because somebody kept requesting different urls on the server with referer spam. The tutorial shows how to block <a href="http://en.wikipedia.org/wiki/Referer_spam">referer spam</a> on a <a href="http://www.debian.org/">Debian 3.1 server</a> with a <a href="http://www.apache.org/">apache 2 webserver</a> by using <a href="http://www.modsecurity.org/">mod_security</a>
<br />
&nbsp;
<br />


<strong>Install <a href="http://www.modsecurity.org/">mod_security</a></strong>

```


```

debian21:~# apt-get install libapache2-mod-security
Reading Package Lists... Done
Building Dependency Tree... Done
The following extra packages will be installed:
  mod-security-common
The following NEW packages will be installed:
  libapache2-mod-security mod-security-common
0 upgraded, 2 newly installed, 0 to remove and 0 not upgraded.
Need to get 274kB of archives.
After unpacking 737kB of additional disk space will be used.
Do you want to continue? [Y/n]
Get:1 http://mirrors.sunsite.dk stable/main mod-security-common 1.8.7-1 [240kB]
Get:2 http://mirrors.sunsite.dk stable/main libapache2-mod-security 1.8.7-1 [34,4kB]
Fetched 274kB in 0s (682kB/s)
Selecting previously deselected package mod-security-common.
(Reading database ... 28605 files and directories currently installed.)
Unpacking mod-security-common (from .../mod-security-common_1.8.7-1_all.deb) ...
Selecting previously deselected package libapache2-mod-security.
Unpacking libapache2-mod-security (from .../libapache2-mod-security_1.8.7-1_i386.deb) ...
Setting up libapache2-mod-security (1.8.7-1) ...
Setting up mod-security-common (1.8.7-1) ...
debian21:~#

```


```


<strong>Enable the newly installed module</strong>

```


```

debian21:~# a2enmod mod-security
Module mod-security installed; run /etc/init.d/apache2 force-reload to enable.
debian21:~#

```


```



<strong>Add this setup to your apache2.conf or your .htaccess file</strong>

```


```

<ifmodule mod_security.c>
    # Turn the filtering engine On or Off
    SecFilterEngine On
    
    # Make sure that URL encoding is valid
    SecFilterCheckURLEncoding On

    # Unicode encoding check
    SecFilterCheckUnicodeEncoding Off

    # Only allow bytes from this range
    SecFilterForceByteRange 0 255
    
    # Only log suspicious requests
    SecAuditEngine RelevantOnly
    
    # The name of the audit log file
    #SecAuditLog logs/audit_log
    # Debug level set to a minimum
    #SecFilterDebugLog logs/modsec_debug_log    
    #SecFilterDebugLevel 0
    
    # Should mod_security inspect POST payloads
    SecFilterScanPOST On
    
    # By default log and deny suspicious requests
    # with HTTP status 500
    SecFilterDefaultAction "deny,log,status:500"

    # Block request with suspicious referers
    SecFilterSelective "HTTP_REFERER" "(holdem|poker|casino|porn)" deny,nolog,status:500
</ifmodule>

```


```


<strong>And then restart apache</strong>

```


```

debian21:~# /etc/init.d/apache2 restart
Forcing reload of web server: Apache2.
debian21:~#

```


```


<strong>Then run a few test requests to ensure it works as we intended it to</strong>

```


```

debian21:~# wget http://localhost/ --referer=http://www.holdem.com
--15:33:34--  http://localhost/
           => `index.html'
Resolving localhost... 127.0.0.1
Connecting to localhost[127.0.0.1]:80... connected.
HTTP request sent, awaiting response... 500 Internal Server Error
15:33:34 ERROR 500: Internal Server Error.

debian21:~#

```


```


It blocks the request just like we thought it would.


```


```

debian21:~# wget http://localhost/ --referer=http://www.google.com
--15:33:43--  http://localhost/
           => `index.html'
Resolving localhost... 127.0.0.1
Connecting to localhost[127.0.0.1]:80... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1,009 [text/html]

100%[========================================>] 1,009         --.--K/s

15:33:43 (9.62 MB/s) - `index.html' saved [1009/1009]

debian21:~#

```


```



The request passed right trough as intended ;)



<strong>And we are done.</strong>
This is only one way of preventing referer spam, <a href="http://www.adsensechat.com/showthread.php?t=601">some others</a> have done a similar block by using the built-in Linux firewall called iptables. Perhaps more on using iptables as blocking mechanism another time.

