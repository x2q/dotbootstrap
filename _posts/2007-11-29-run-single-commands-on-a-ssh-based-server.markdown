---
layout: post
published: true
title: Run Single Commands on a SSH-based Server
permalink: /run-single-commands-on-a-ssh-based-server/
wordpress_id: 550
categories:
- Links
- Linux
- Open Standards
- Open Source
- Debian
- Ubuntu
- Fedora
- SSH
- ssh single command
- ssh execute single command
- ssh run single command
---


You can run a single command on an <a href="http://en.wikipedia.org/wiki/OpenSSH">OpenSSH</a> server by adding the command to the end of the ssh command.


```

ssh -fCT user@server <command>

-f = Allows ssh to close after the connection is established.
-C = Use Compression
-T = No terminal session will be started
</command>
```

