---
layout: post
published: true
title: ! 'Howto: Create your own Debian or Ubuntu package repository'
permalink: /howto-create-your-own-debian-or-ubuntu-package-repository/
wordpress_id: 563
categories:
- Links
- Linux
- Open Standards
- Open Source
- Debian
- Ubuntu
- html
- ubuntu repository howto
- create ubuntu repository
- create debian repository
- ubuntu package howto
- ubuntu create package
---


The <a href="http://en.wikipedia.org/wiki/Debian">Debian</a> <a href="http://en.wikipedia.org/wiki/Package_management_system">package management system</a> (called <a href="http://en.wikipedia.org/wiki/Advanced_Packaging_Tool">Advanced Packaging Tool or APT</a>) is by far the most well-designed and is one of the top <a href="http://en.wikipedia.org/wiki/Killer_application">killer features</a> on the <a href="http://en.wikipedia.org/wiki/Linux">Linux platform</a>.

This short Howto describes howto establish a <a href="http://en.wikipedia.org/wiki/Deb_(file_format)">Debian package</a> repository for home-grown <a href="http://en.wikipedia.org/wiki/Deb_(file_format)">deb-packages</a> or like (could be used for Ubuntu as well, since Ubuntu uses the Debian package management system).


<strong>Establish repository structure</strong>
Create the repository structure in a directory. E.g. in ~/public_html directory exposed to the web.


```

cd public_html
mkdir my-repository
cd my-repository
mkdir binary
mkdir source

```






<strong>Copy your <a href="http://en.wikipedia.org/wiki/Deb_(file_format)">deb-packages</a> into the repository</strong>

```

Like this
cp src/bzr_0.11-1.1_all.deb public_html/my-repository/binary/

```


<strong>Install the tools to be able to create a repository index</strong>

```

sudo aptitude install dpkg-dev

```


<strong>Create a repository index</strong>
cd my-repository
dpkg-scanpackages binary /dev/null | gzip -9c > binary/Packages.gz
dpkg-scansources source /dev/null | gzip -9c > source/Sources.gz

<strong>Using the repository</strong>


```

# Add these two lines into the /etc/apt/sources.list
deb http://myhost.com/~cc/my-repository binary/
deb-src http://myhost.com/~cc/my-repository source/

```



Feel free to comment - easier methods and tips are more than welcome ;)


<strong>For a more professional package management setup, use <a href="http://www.debian-administration.org/articles/286">reprepro</a></strong>
