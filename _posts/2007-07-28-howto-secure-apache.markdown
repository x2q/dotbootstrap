---
layout: post
published: true
title: Howto Secure Apache
permalink: /howto-secure-apache/
wordpress_id: 483
categories:
- News
- Linux
- Open Standards
- apache
- Open Source
- Debian
- Ubuntu
- Fedora
- security
- hosting
- cgi
- chroot
- web root
- securing apache 2 2
---
<ol>
<li>Use the latest and most current version. Right now the latest is the Apache 2.2 series</li>
<li>Make sure you've installed all the latest security patches</li>
<li>Hide the Apache Version number, and other sensitive information</li>
	<li>Make sure apache is running under its own user account and group</li>
	<li>Ensure that files outside the web root are not served</li>
	<li>Turn off directory browsing (mod_autoindex)</li>
	<li>Turn off server side includes (SSI)</li>
	<li>Turn off CGI execution</li>
	<li>Don't allow apache to use symbolic links</li>
	<li>Turning off multiple Options</li>
	<li>Turn off support for .htaccess files</li>
	<li>Use the Apache mod_security</li>
	<li>Disable all unnecessary modules</li>
	<li>Make sure only root has read access to apache's config and binaries</li>
	<li>Lower the Timeout value</li>
	<li>Limiting large requests</li>
	<li>Limiting Concurrency</li>
	<li>Restricting Access by IP</li>
	<li>Adjusting KeepAlive settings</li>
	<li>Run Apache in a Chroot environment</li>
</ol>

Feel free to post suggestions or corrections :)




