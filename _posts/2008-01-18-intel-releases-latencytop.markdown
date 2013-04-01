---
layout: post
published: true
title: Intel Releases LatencyTop 0.1
permalink: /intel-releases-latencytop/
wordpress_id: 590
categories:
- News
- Linux
- Usability
- Open Source
- Debian
- Ubuntu
- Fedora
- user experience
- latency
- Intel
- LatencyTop 0.1
- software developers
---


<blockquote>The <a href="http://software.intel.com/en-us/oss/">Intel Open Source Technology Center</a> is pleased to announce the release of version 0.1 of LatencyTOP, a tool for developers to visualize system latencies. Slow servers, skipping audio, jerky video - everyone knows the symptoms of latency. But to know what's really going on in the system, what's causing the latency, and how to fix it... Those are difficult questions without good answers right now. LatencyTOP is a <a href="http://en.wikipedia.org/wiki/Linux">Linux</a> tool for software developers (both <a href="http://en.wikipedia.org/wiki/Linux_kernel">kernel</a> and userspace), aimed at identifying where system latency occurs, and what kind of operation/action is causing the latency to happen. By identifying this, developers can then change the code to avoid the worst latency hiccups.</blockquote>

<blockquote>
LatencyTOP is a <a href="http://en.wikipedia.org/wiki/Linux">Linux tool</a> for software developers (both <a href="http://en.wikipedia.org/wiki/Linux_kernel">kernel</a> and userspace), aimed at identifying where system latency occurs, and what kind of operation/action is causing the latency to happen. By identifying this, developers can then change the code to avoid the worst latency hiccups.

There are many types and causes of latency, and LatencyTOP focus on type that causes audio skipping and desktop stutters. Specifically, LatencyTOP focuses on the cases where the applications want to run and execute useful code, but there's some resource that's not currently available (and the kernel then blocks the process). This is done both on a system level and on a per process level, so that you can see what's happening to the system, and which process is suffering and/or causing the delays.
</blockquote>

I have used <a href="http://en.wikipedia.org/wiki/Powertop">PowerTop</a> from <a href="http://software.intel.com/en-us/oss/">Intel</a> to optimize my laptop's battery time. <a href="http://en.wikipedia.org/wiki/Powertop">PowerTop</a> is really a great tool to identify wasted CPU cycles and unnecessary wake ups, and it is a great contribution from <a href="http://software.intel.com/en-us/oss/">Intel</a> to <a href="http://en.wikipedia.org/wiki/Linux">Linux</a> and the open source community.

And now they (with <a href="http://www.fenrus.org/">Arjan van de Ven</a> in front, a long time <a href="http://en.wikipedia.org/wiki/Linux_kernel">Linux kernel contributor</a>) releases this LatencyTop, which also got a great potential to improve the user experience and usability for <a href="http://en.wikipedia.org/wiki/Linux">Linux</a> users and coming users.

<a href="http://www.fenrus.org/">Arjan van de Ven</a> and <a href="http://software.intel.com/en-us/oss/">Intel</a> thank you for a great <a href="http://en.wikipedia.org/wiki/Linux">Linux</a> tool.


Read more at <a href="http://www.latencytop.org/">latencytop.org</a>.
