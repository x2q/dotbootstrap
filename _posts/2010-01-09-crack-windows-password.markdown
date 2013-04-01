---
layout: post
published: true
title: Crack Windows Password
permalink: /crack-windows-password/
wordpress_id: 923
categories:
- News
- Crack
- MySQL
- hack
- ssl
- cisco
- VNC
- smb
- password
- http
- telnet
- Samba
- FTP
- POP3
- IMAP
- HTTP Auth
- LDAP
- NNTP
- ICQ
- Socks5
- PCNFS
- network drive
- windows network
- network share
- target server
- SNMP
- attempt server
- web address
---


THC-Hydra - the best parallized login hacker: for Samba, FTP, POP3, IMAP, Telnet, HTTP Auth, LDAP, NNTP, MySQL, VNC, ICQ, Socks5, PCNFS, Cisco and more.


<strong>Download THC-Hydra, extract and compile</strong>


```

wget http://freeworld.thc.org/releases/hydra-5.4-src.tar.gz
tar zxvf hydra-5.4-src.tar.gz
cd hydra-5.4-src
./configure --disable-xhydra --prefix=~/bin
make
make install

```




```

Hydra v5.4 [http://www.thc.org] (c) 2009 by van Hauser / THC <vh @thc.org>

Syntax: hydra [[[-l LOGIN|-L FILE] [-p PASS|-P FILE]] | [-C FILE]] [-e ns]
 [-o FILE] [-t TASKS] [-M FILE [-T TASKS]] [-w TIME] [-f] [-s PORT] [-S] [-vV]
 server service [OPT]

Options:
  -R        restore a previous aborted/crashed session
  -S        connect via SSL
  -s PORT   if the service is on a different default port, define it here
  -l LOGIN or -L FILE login with LOGIN name, or load several logins from FILE
  -p PASS  or -P FILE try password PASS, or load several passwords from FILE
  -e ns     additional checks, "n" for null password, "s" try login as pass
  -C FILE   colon seperated "login:pass" format, instead of -L/-P options
  -M FILE   server list for parallel attacks, -T TASKS sets max tasks per host
  -o FILE   write found login/password pairs to FILE instead of stdout
  -f        exit after the first found login/password pair (per host if -M)
  -t TASKS  run TASKS number of connects in parallel (default: 16)
  -w TIME   defines the max wait time in seconds for responses (default: 30)
  -v / -V   verbose mode / show login+pass combination for each attempt
  server    the target server (use either this OR the -M option)
  service   the service to crack. Supported protocols: [telnet ftp pop3 imap smb
 smbnt http https http-proxy cisco cisco-enable ldap mssql mysql nntp vnc rexec
socks5 snmp cvs icq pcnfs sapr3 ssh2 smtp-auth]
  OPT       some service modules need special input (see README!)

Use HYDRA_PROXY_HTTP/HYDRA_PROXY_CONNECT and HYDRA_PROXY_AUTH env for a proxy.
Hydra is a tool to guess/crack valid login/password pairs - use allowed only for

legal purposes! If used commercially, name and web address must be mentioned in
the report. You can always find the newest version at http://www.thc.org
</vh>
```
