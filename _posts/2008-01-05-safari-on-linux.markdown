---
layout: post
published: true
title: Safari on Linux
permalink: /safari-on-linux/
wordpress_id: 562
categories:
- Links
- Linux
- Open Standards
- Webdesign
- Open Source
- Debian
- Ubuntu
- Fedora
- OSX
- wine
- Safari
- safari linux
- safari for linux
- safari linux download
- download safari for linux
- safari download linux
- Erich Schubert
---


This is a four step guide to get <a href="http://en.wikipedia.org/wiki/Safari_%28web_browser%29">Apple's Safari browser</a> running on <a href="http://en.wikipedia.org/wiki/Linux">Linux</a>.

<ol>

	<li>Run winecfg, set <a href="http://en.wikipedia.org/wiki/Microsoft_Windows">Windows</a> version to <a href="http://en.wikipedia.org/wiki/Microsoft_Windows">WinXP</a></li>

	<li>Copy the core windows fonts: cp /usr/share/fonts/truetype/msttcorefonts/{Arial,Times_New_Roman}*.ttf ~/.wine/drive_c/windows/fonts/</li>

	<li>Download Safari for Windows from the <a href="http://www.apple.com/safari/">Apple homepage</a></li>



	<li>Run the Safari installer with Wine. Do not install <a href="http://en.wikipedia.org/wiki/Bonjour_(software)">Bonjour</a> or the Apple updater</li>

	<li>Run Safari</li>

</ol>

Remind that the <a href="http://packages.debian.org/search?keywords=msttcorefonts">msttcorefonts</a> is required ;)


<a href="http://techhamlet.com/2012/03/how-to-easily-install-safari-in-linux-the-new-updated-guide/">Thanks to Erich Schubert for providing the guide</a>


