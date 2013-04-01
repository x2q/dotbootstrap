---
layout: post
published: true
title: Howto install HipHop for PHP on Ubuntu
permalink: /howto-install-hiphop-for-php-on-ubuntu/
wordpress_id: 951
categories:
- News
- apache
- Ubuntu
- PHP
- performance
- hiphop
- facebook
- gcc
- compile
- llvm
- Zend
- LAMP
- C++
---
&nbsp;

HipHop is a source code transformer which transforms PHP source code into highly optimized C++ and then compiles it using g++.

<strong>Required packages</strong>

```
sudo apt-get install cmake g++ libboost-dev flex bison re2c libmysqlclient-dev libxml2-dev libmcrypt-dev libicu-dev openssl binutils-dev libcap-dev libgd2-xpm-dev zlib1g-dev libtbb-dev libonig-dev libpcre3-dev git-core autoconf libtool libcurl4-openssl-dev libboost-system-dev libboost-program-options-dev libboost-filesystem-dev
```

<strong>Get the HipHop source-code</strong>

```
mkdir hiphop
cd hiphop
git clone git://github.com/facebook/hiphop-php
cd hiphop-php
export CMAKE_PREFIX_PATH=`/bin/pwd`/../
export HPHP_HOME=`/bin/pwd`
export HPHP_LIB=`/bin/pwd`/bin
git submodule init
git submodule update
cd ..
```

<strong>Building third-party libraries</strong>

<em>libevent</em>

```
wget http://www.monkey.org/~provos/libevent-1.4.13-stable.tar.gz
tar -xzvf libevent-1.4.13-stable.tar.gz
cd libevent-1.4.13-stable
cp ../hiphop-php/src/third_party/libevent.fb-changes.diff .
patch < libevent.fb-changes.diff
./configure --prefix=$CMAKE_PREFIX_PATH
make
make install
cd ..
```

<em>ICU4</em>

```
wget http://download.icu-project.org/files/icu4c/4.2.1/icu4c-4_2_1-src.tgz
tar -xvzf icu4c-4_2_1-src.tgz
cd icu/source
./configure --prefix=$CMAKE_PREFIX_PATH
make
make install
cd ../../
```

<em>libCurl</em>

```
wget http://curl.haxx.se/download/curl-7.20.0.tar.gz
tar -xvzf curl-7.20.0.tar.gz
cd curl-7.20.0
cp ../hiphop-php/src/third_party/libcurl.fb-changes.diff .
patch -p1 < libcurl.fb-changes.diff
./configure --prefix=$CMAKE_PREFIX_PATH
make
make install
cd ..
```

<strong>Build HipHop</strong>

```
cd hiphop-php
cmake .
make
```
