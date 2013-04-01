---
layout: post
published: true
title: Howto PHP / Java bridge on Debian
permalink: /howto-php-java-bridge-on-debian/
wordpress_id: 162
categories:
- News
- Linux
- Open Source
- Debian
- Java
- PHP
- Java bridge
- php java bridge
- php java bridge tutorial
- php java bridge debian
---


<strong>Updated 20. Marts 2007</strong>

The PHP / Java Bridge makes it possible to run use java objects within your PHP code. For example; let's say you have a jar-file containing some functionality you may want to use in a PHP application.

To use this you must have a Java installed - either the latest version of Java (JDK) or a black hawk version installed.

Get the source code php-java-bridge_3.0.4.tar.bz2 from the <a href="http://sourceforge.net/projects/php-java-bridge">PHP / Java bridge website</a> and unpack it with

```

wget http://switch.dl.sourceforge.net/sourceforge/php-java-bridge/php-java-bridge_3.0.8.tar.bz2

```


```

tar xvjf php-java-bridge_3.0.4.tar.bz2

```


```

cd php-java-bridge-3.0.4

```


```

phpize - in order to use this you'll need to have the php5-dev package installed

```


```

./configure --with-java=/usr/lib/j2sdk1.5-sun - be sure to set this to the path where the Java installation is located

```




If the ./configure command fails because the automake version is less than 1.6 try this

```

apt-get install automake1.6
update-alternatives --config automake

```


Select version 1.6 of automake in the update-alternatives dialog and then try to run ./configure again

<strong>Now we just need to compile and install, this is done by:</strong>

```

make
make install-modules

```


<strong>Add this line to php.ini in order to enabled the PHP/Java bridge extension:</strong>

```

extension=java.so

```




