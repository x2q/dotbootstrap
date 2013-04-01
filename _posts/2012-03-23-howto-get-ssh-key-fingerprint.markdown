---
layout: post
published: true
title: ! 'Howto: Get SSH Key Fingerprint'
permalink: /howto-get-ssh-key-fingerprint/
wordpress_id: 1974
categories:
- Howto
- Linux
- Debian
- SSH
- git
- fingerprint
- github
---
<img class="alignright size-full wp-image-1993" title="openssh" src="http://lh6.ggpht.com/-FveNZJO--Ys/UVmAAg9OsSI/AAAAAAAAFzI/s-r-DJSJ1do/openssh.png" alt="openssh" width="578" height="191" />Recently Github was hit by a <a href="https://github.com/blog/1068-public-key-security-vulnerability-and-mitigation">Public Key Security Vulnerability</a> and asked all users to review their keys.

Then they showed me the following fingerprint (80:01:12:a0:5e:59:40:cb:7a:dd:60:8e:75:86:c2:d7) and asked me to review. The the question was, how do I get the fingerprint of my public ssh key.


```

ssh@ssh:~$ ssh-keygen -l -f ~/.ssh/*.pub
1024 80:01:12:a0:5e:59:40:cb:7a:dd:60:8e:75:86:c2:d7 ssh@sshkeyhost.com (DSA)

```
