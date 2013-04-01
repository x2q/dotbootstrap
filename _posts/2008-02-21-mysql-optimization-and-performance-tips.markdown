---
layout: post
published: true
title: MySQL Optimization and Performance Tips
permalink: /mysql-optimization-and-performance-tips/
wordpress_id: 598
categories:
- News
- Linux
- Open Source
- Debian
- Ubuntu
- Fedora
- MySQL
- Oracle
- FreeBSD
---
<ul>
	<li>Store IP addresses as INT, not CHAR - by using INET_ATON to convert from a string to an integer and by using INET_NTOA to convert from an integer to a string</li>

	<li>Use non-persistent connection, since they are light-weight - much faster create than compared Oracle or PostgreSQL</li>




	<li>Use the right storage engine; this means for example the ARCHIVE-engine for logs and other kind of INSERT-only operations, and the MEMORY-engine for fast in-memory data that should go away on server restart</li>


</ul>


More general MySQL optimization and performance tips are available in this <a href="http://www.slideshare.net/techdude/how-to-kill-mysql-performance">Slideshow</a>.

