---
layout: post
published: true
title: Howto migrate from CVS to SVN using CVS2SVN
permalink: /howto-migrate-from-cvs-to-svn-using-cvs2svn/
wordpress_id: 495
categories:
- Links
- News
- Linux
- Open Standards
- Open Source
- CVS
- svn
- cvs2svn
- cvs to svn migration
- cvs2svn tutorial
- migrate cvs to svn
- cvs2svn windows
- cvs svn migration
---


This howto explains how I migrated my personal code <a href="http://en.wikipedia.org/wiki/Concurrent_Versions_System">CVS</a> repositories to <a href="http://en.wikipedia.org/wiki/Subversion_%28software%29">Subversion</a> aka <a href="http://en.wikipedia.org/wiki/Subversion_%28software%29">svn</a>. Some will argue that the easiest way to migrate is by exporting a <a href="http://en.wikipedia.org/wiki/Concurrent_Versions_System">CVS</a> module and then import it into <a href="http://en.wikipedia.org/wiki/Subversion_%28software%29">svn</a>, but such an approach doesn't preserve the commit history etc. To do a "real" and history preserving migration I use a tool called <a href="http://cvs2svn.tigris.org/">cvs2svn</a> capable of converting all historic entries from <a href="http://en.wikipedia.org/wiki/Concurrent_Versions_System">CVS</a> to <a href="http://en.wikipedia.org/wiki/Subversion_%28software%29">Subversion</a>.


First I create a new home for the code using svnadmin

```

svnadmin create --fs-type fsfs /var/svn/myproject

```


Then fire the cvs2svn conversion 

```

cvs2svn --existing-svnrepos -s /var/svn/myproject /var/cvs/myproject

```


The cvs2svn process then create a number of Subversion commits like

```

...
Creating Subversion commit 303 (commit)
Creating Subversion commit 304 (commit)
Creating Subversion commit 305 (commit)
Creating Subversion commit 306 (commit)
Creating Subversion commit 307 (commit)
Creating Subversion commit 308 (commit)

```



