---
layout: post
published: true
title: Howto create a subversion(svn) file based repository
permalink: /howto-create-a-subversion-svn-file-based-repository/
wordpress_id: 190
categories:
- Links
- Usability
- Open Standards
- svn create repository
---
<a href="http://lh6.ggpht.com/-xq1rlT6njgo/UVl850j1KSI/AAAAAAAAFg4/Fr3gxLcbuIE/svn-checkout.png"><img src='http://lh6.ggpht.com/-9Ysi_jXCGrg/UVl842A9U2I/AAAAAAAAFgw/voEMshzktc8/thumb-svn-checkout.png' alt='SVN Checkout dialog' /></a>


<strong>Create the repository on the server</strong>

```
svnadmin create --fs-type fsfs /home/cc/MyNewProject
```


And then I'm able to access the repository trough this URL:

```
svn+ssh://cc@debian06.myhost.dk/home/cc/MyNewProject
```



