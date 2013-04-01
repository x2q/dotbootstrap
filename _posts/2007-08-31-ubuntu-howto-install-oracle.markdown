---
layout: post
published: true
title: ! 'Ubuntu Howto: Install Oracle'
permalink: /ubuntu-howto-install-oracle/
wordpress_id: 497
categories:
- Links
- News
- Linux
- Open Source
- Debian
- Ubuntu
- Oracle
- databases
- Public Key
- web interface
- database software
- the Oracle
- ubuntu oracle client
- install oracle on ubuntu
- install oracle ubuntu
- oracle client ubuntu
- ubuntu oracle
---


Installing Oracle on Ubuntu is fairly easy, since Oracle has created a Debian and Ubuntu package repository, so it is possible to download and install the Oracle database software using apt-get and aptitude.

Howto use the Oracle Debian and Ubuntu Repository:

Add the following lines to the /etc/apt/sources.list

```

# Oracle Repository
deb http://oss.oracle.com/debian unstable main non-free

```


Update the package repository database with:

```

cc@ray:~$ sudo apt-get update

```


Now you should be able to install the following Oracle software:
<ul>
	<li>libaio</li>
	<li>oracle-xe-client</li>
	<li>oracle-xe</li>
	<li>oracle-xe-universal</li>
</ul>

Install the Oracle Express packages

```

sudo aptitude install oracle-xe oracle-xe-client

```


Configure using:

```

sudo /etc/init.d/oracle-xe configure

```



Access the nice Oracle web interface by pointing your Firefox to:

```

http://127.0.0.1:8080/apex

```



Updated:
The installation process might report that the Oracle packages are not gpg signed, but you should be able to install the packages anyway.

You can avoid this report by added the Oracle gpg-public key to your apt-key chain

```

wget http://oss.oracle.com/el4/RPM-GPG-KEY-oracle  -O- | sudo apt-key add - 

```



Read more on Oracle and Debian and Ubuntu <a href="http://www.oracle.com/technetwork/topics/linux/whatsnew/index.html">here</a>
