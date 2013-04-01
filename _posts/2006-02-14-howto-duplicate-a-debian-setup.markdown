---
layout: post
published: true
title: Howto duplicate a debian setup
permalink: /howto-duplicate-a-debian-setup/
wordpress_id: 178
categories:
- Links
- Linux
- target server
---
First we need to extract the installed packages on the source server and save them in a file


```

debian:~# dpkg --get-selections >> packages

```



Now we move to the target server and set the package selections according to the package file we just created on the source machine.

```

debian:~# dpkg --set-selections < < packages

```


Now we just need to run this in order to actually install the packages.

```

```

debian:~# apt-get -u dselect-upgrade

```


