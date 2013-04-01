---
layout: post
published: true
title: Howto Access via ssh a Virtualbox Guest machine
permalink: /howto-access-via-ssh-a-virtualbox-guest-machine/
wordpress_id: 570
categories:
- Links
- Linux
- Open Standards
- Open Source
- Debian
- Ubuntu
- Fedora
- Tutorial
- SSH
- virtualbox ssh
- virtualbox ssh to guest
- ssh virtualbox
- ssh into virtualbox
- ssh to virtualbox
- Network Address Translation
---




<blockquote>
By default, the network connection in VirtualBox is set to NAT (Network Address Translation), that is every packet coming from the Guest machine is modified so that it seems as it has come from the Host machine. In this way it&acirc;&euro;&trade;s easy for the Guest machine to connect to all the rest of the network (the internet included) but nobody can start a connection with the Guest Machine since it&acirc;&euro;&trade;s hidden behind the Host one.
</blockquote>

This <a href="http://mydebian.blogdns.org/?p=148">blog post</a> describes a technique to route incoming connections to VirtualBox guest instances in order to enable for example SSH and sshfs connections


