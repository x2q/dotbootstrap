---
layout: post
published: true
title: ! 'Linux How to: Add a existing user to existing group'
permalink: /linux-how-to-add-a-existing-user-to-existing-group/
wordpress_id: 970
categories:
- News
- Linux
- Debian
- Ubuntu
- admin
- /etc/passwd
- usermod
- adduser
- man
- /etc/group
---


<strong>usermod example</strong>

Add existing user john to admin supplementary/secondary group with usermod command using -a option ~ i.e. add the user to the supplemental group(s). Use only with -G option:


```

# usermod -a -G admin john

```


Change existing user john primary group to mail:

```

# usermod -g mail tony

```
