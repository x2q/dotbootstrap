---
layout: post
published: true
title: Howto Upgrade Joomla
permalink: /howto-upgrade-joomla/
wordpress_id: 165
categories:
- Links
- Linux
- Open Standards
- Joomla
- Open Source
- Debian
- Ubuntu
- joomla update
- update joomla
- joomla update howto
- upgrade joomla
- how to upgrade joomla
---


Download the latest <a href="http://en.wikipedia.org/wiki/Joomla">Joomla</a> patch version - here I'm going to upgrade Joomla version 1.0.7 to 1.0.13. The latest reeases of Joomla is always avaible at the <a href="http://forge.joomla.org/">Joomla development sourceforge system</a>.

Download the latest file to some path in your system, here I have downloaded it into the <a href="http://en.wikipedia.org/wiki/Joomla">Joomla</a> directory.


```

cd site
tar xvjf Joomla_1.0.7_to_1.0.13-Stable-Patch_Package.tar.bz2
chown -R username:groupname *

```


And you are done - Always remember to do a working backup before upgrade - just in case.

