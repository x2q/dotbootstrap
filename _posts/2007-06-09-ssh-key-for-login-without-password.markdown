---
layout: post
published: true
title: SSH Key for Login Without Password
permalink: /ssh-key-for-login-without-password/
wordpress_id: 415
categories:
- Links
- Linux
- Open Source
- Debian
- Ubuntu
- Fedora
- FreeBSD
- SSH
- private key
- ssh login without password
- ssh keys no password
- ssh no password
- ubuntu ssh without password
- ubuntu ssh no password
- Public Key
- Private
---


ssh-keygen is used to generate that key pair for you and thereby unnecessary to type password on every login.

<strong>Here is a session where your own personal private/public key pair is created:</strong>

```

marge$ ssh-keygen -t rsa
Generating public/private rsa key pair.
Enter file in which to save the key (/user/cc/.ssh/id_rsa):
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /user/cc/.ssh/id_rsa.
Your public key has been saved in /user/cc/.ssh/id_rsa.pub.
The key fingerprint is:
4c:64:4d:05:38:68:0f:d9:83:16:5f:01:ac:e0:5f:98 cc@marge.cs.aau.dk

```


The command ssh-keygen -t rsa initiated the creation of the key pair.
No passphrase was entered (Enter key was pressed instead).

The private key was saved in .ssh/id_rsa. This file is read-only and only for you. No one else must see the content of that file, as it is used to decrypt all correspondence encrypted with the public key.

The public key is save in .ssh/id_rsa.pub.

<strong>In this case, the content of file id_rsa.pub is</strong>

```

ssh-rsa AAAAB3NzaC1yc2EAAAABIwAAAQEAs5TlojsVbzYX6069n
Y0NdtltH6fIktJSKq+HbGnN+OvqKR1d+zt4fTO52YIStcUhwhxMVc
GkxXnDyU4OGuW76TuYn2lw/nfkvl7brlf/iUfQ1FNhjfKspTWZ3VL1
z8sxZ4kHeeb/iXrTNfoePuiMcUW8WcoOR1u2MgDb7o64X1Qzbv7
nho9gzoeieQmK9b8jHwNQEWiUR1zTd0jkQxPBpx5OGBEKhW7ilw0
hsgkugwrOWUsg842Mpikxu4IFAcMGo/vHmfWZ/hrLJbvX8Bo7/ue
oErdSLOWNcTJczTp9FQL+dExvvLBEjAO3BsjtzRROVnUFTt11mxf
qZs+/MWJ9Qw== cc@marge.cs.aau.dk

```


Its content is then copied in file .ssh/authorized_keys of the system you wish to SSH to without being prompted for a password. 

<strong>Articles on using OpenSSH for passwordless logins</strong>
<a href="http://www.hackinglinuxexposed.com/articles/20021211.html"> Secure Passwordless Logins with SSH, Part 1</a>, 
<a href="http://www.hackinglinuxexposed.com/articles/20021226.html">Part 2</a>, <a href="http://www.hackinglinuxexposed.com/articles/20030109.html">Part 3</a>, <a href="http://www.hackinglinuxexposed.com/articles/20030115.html">Part 4</a>

