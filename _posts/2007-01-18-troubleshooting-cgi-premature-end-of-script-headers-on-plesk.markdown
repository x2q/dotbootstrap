---
layout: post
published: true
title: Troubleshooting CGI premature end of script headers on Plesk
permalink: /troubleshooting-cgi-premature-end-of-script-headers-on-plesk/
wordpress_id: 337
categories:
- News
- Linux
- apache
- cgi
- perl
- ASCII
- premature end of script headers python
- Premature end of script headers plesk
- python Premature end of script headers
- Premature end of script headers cgi
---


<ol>
	<li>make sure to upload the script into the cgi-bin in ASCII mode</li>
	<li>check permissions - chmod 755 the script</li>
	<li>check ownerships - should be USERID:psacln on the script and the directory should be USERID:psaserv e.g. chown siteuser:psacln test.pl</li>
	<li>make sure that the site has CGI support ticked</li>
	<li>verify the syntax of the script by running "perl -c test.pl"</li>
</ol>
