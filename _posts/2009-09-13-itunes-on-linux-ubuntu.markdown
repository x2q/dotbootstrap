---
layout: post
published: true
title: iTunes on Linux (Ubuntu)
permalink: /itunes-on-linux-ubuntu/
wordpress_id: 842
categories:
- News
- Linux
- Ubuntu
- iPhone
- wine
- Apple
- iTunes
- iPhone 3GS
- activation
- USD
- itunes ubuntu
- itunes for ubuntu
- itunes linux
- itunes for linux
- ubuntu itunes
---



<img src="http://lh3.ggpht.com/-Y_BdTdbDKP8/UVl_3EvV81I/AAAAAAAAFyY/0UAZpJfC_G8/250px-itunes9mac.png" alt="iTunes 9" title="iTunes 9" width="250" height="152" class="size-full wp-image-846" />

I bought the new <a href="http://www.apple.com/iphone/">iPhone 3GS</a> and in order to use the phone I needed to actually activate the phone using Apple iTunes. Nomally iTunes and <a href="http://www.ubuntu.com/">Ubuntu</a> is a no-go, however using the latest <a href="http://www.winehq.org/">wine</a> from the <a href="http://www.ubuntu.com/">Ubuntu</a> it is possible out of the box - I' really impressed of the <a href="http://www.winehq.org/">wine project</a>.



<strong>What you need</strong>

Check that you got the at least the following wine version:

```

$ dpkg -l | grep wine | awk '{ print $2, " ",$3}'
wine             1.1.29~winehq0~ubuntu~9.04-0ubuntu2
wine-gecko    1.0.0-0ubuntu1

```


If not, then install wine:

```

$ sudo aptitude install wine wine-gecko

```

 
Then <a href="http://support.apple.com/kb/DL928">download iTunes 8.x</a> (important to download version 8.x otherwise it doesn't work out of the box)

```

$ wget wget http://appldnld.apple.com.edgesuite.net/content.info.apple.com/iTunes8/061-6717.20090715.XsE4R/iTunesSetup.exe

```


Then just run the install process
$ wine iTunesSetup.exe

And finally start iTunes.
