---
layout: post
published: true
title: Linux I/O Redirection
permalink: /linux-io-redirection/
wordpress_id: 665
categories:
- News
- Linux
- unix
- Bash
- stdout
- stderr
- stdin
- linux io redirection
---


<strong>Definitions in Unix/Linux/*Nix I/O</strong>
<ul>
	<li>0 = stdin</li>
	<li>1 = stdout</li>
	<li>2 = stderr</li>
</ul>


<strong>The following command saves (redirects) stdout and stderr to the files "out.txt" and "err.txt", respectively</strong>


```

# command 1>out.txt 2>err.txt

```



<strong>The following command redirects stdout to the file out.txt and stderr to stdout</strong>


```

# command > out.txt 2>&1

```



This was just some simple examples - <a href="http://www.cpqlinux.com/">read more about Linux I/O Redirection here</a>.
