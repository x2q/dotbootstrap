---
layout: post
published: true
title: ! 'Trigger a puppetd run on all hosts: Pupperrun all alternative'
permalink: /trigger-a-puppetd-run-on-all-hosts-pupperrun-all-alternative/
wordpress_id: 861
categories:
- News
- puppet
- puppetd
- puppetrun
- xargs
- USD
- db01.domain.com
- app01.domain.com
---


Puppetrun is used to connect to a set of machines running puppetd and trigger them to run their configurations. The most common usage would be to specify a class of hosts and a set of tags, and puppetrun would look up in LDAP all of the hosts matching that class, then connect to each host and trigger a run of all of the objects with the specified tags, however if the host configurations is not stored in LDAP, you must specify hosts manually, e.g. puppetrun app01.domain.com and puppetrun db01.domain.com

However using the following command, you can loop through all the hosts subscripted in puppetca and trigger a pupperun on each of them.


```

puppetca --list --all | awk '{ print $2 }' | xargs -I &rsquo;{}&rsquo; sudo puppetrun --host &rsquo;{}&rsquo;

```
