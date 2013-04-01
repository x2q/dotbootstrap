---
layout: post
published: true
title: ! 'Firefox Flash Interaction Bug: I Cannot Click In Flash Application e.g.
  Youtube'
permalink: /firefox-flash-interaction-bug-i-cannot-click-in-flash-application-e-g-youtube/
wordpress_id: 938
categories:
- News
- Linux
- Ubuntu
- Firefox
- flash
- Adobe
- google
- Google Analytics
- bug
- Youtube
- Adobe Flash
- Chrome
- Microsoft Windows
---


I experienced recently that I was unable to hit and click in flash based application using the mouse, which meant that I was forced to use the keyboard to navigate in all flash application - not a good user experience and very annoying. Adobe Flash does simply not register any mouse clicks (e.g. on YouTube, Google Analytics, etc.).

However I have researched on the bug, actually it was quite difficult to find anyone, who had experienced problem and reported it, also because the problem is hard to describe consistently. This fact was also clear, when I read the <a href="https://bugs.launchpad.net/ubuntu/+source/flashplugin-nonfree/+bug/410407">Ubuntu bug report</a>.

The descriptions of the problem varies a lot: "Clicking on items in Flash player does nothing", "I Cannot Click On Flash In Ubuntu", "Flash does not register any clicks", and "flash does not recognise mouse clicks".

<strong>Solution</strong>

<ul>
	<li>Hit ALT+F2 and enter</li>

	<li>gksudo gedit /usr/lib/nspluginwrapper/i386/linux/npviewer</li>

	<li>add the following line BEFORE the last line of text</li>

	<li>export GDK_NATIVE_WINDOWS=1</li>

	<li>Save.</li>

	<li>Restart any applications using flash</li>
</ul>

