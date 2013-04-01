---
layout: post
published: true
title: ! 'Howto: Convert an OpenSSL key to a public/private OpenSSH key-pair'
permalink: /howto-convert-an-openssl-key-to-a-publicprivate-openssh-key-pair/
wordpress_id: 717
categories:
- News
- Linux
- Open Standards
- Open Source
- openSSL
- FreeBSD
- SSH
- NetBSD
- OpenBSD
- ssl
- convert
- OpenSSH
- private key
- Public Key
- Private
- convert cer to pfx
- convert cer to crt
- convert crt to pfx
- convert pfx to cer
---


This howto demonstrates how to convert an OpenSSL key to a public/private OpenSSH key-pair.

The motivation for converting this is simple -- dual use. That is to say, any user or application that has been issued a certificate can now use their SSL-based credentials for both SSL- and SSH-based authentication.

<strong>Requirements</strong>
You'll need a valid certificate and private key -- actually only the key is required.  This recipe assumes that your certificate and key will have the names user-crt.pem and user-key.pem, respectively.  If your key is encrypted (which it should be), you'll also need to have it's passphrase handy.

You'll need a shell account on a system that supports OpenSSH logins using public/private key authentication.

<strong>Solution</strong>
The solution is to extract the public key from the private key using ssh-keygen, copy the new key-pair into place, and test them out.

<strong>1. Copy the private SSL key to ~/.ssh/id_ssl.</strong>
$ cp user-key.pem ~/.ssh/id_ssl
$ chmod 600 ~/.ssh/id_ssl

<strong>2. Extract the public SSH key using ssh-keygen.</strong>
$ ssh-keygen -y -f ~/.ssh/id_ssl > ~/.ssh/id_ssl.pub
$ chmod 600 ~/.ssh/id_ssl.pub

<strong>3. Add the public key to your authorized_keys</strong>
$ cat ~/.ssh/id_ssl.pub >> ~/.ssh/authorized_keys

<strong>4. Test the new key by attempting to SSH to localhost.</strong>
$ ssh -i ~/.ssh/id_ssl localhost

At this point, you'll need to enter your passphrase (assuming you had one), and if all goes well, you'll be sitting at a new shell prompt.

<strong>5. Remove the test key from your authorized_keys file.</strong>

In theory, a single certificate and key issued to an employee would be sufficient to access all participating SSL- and SSH-based resources in a given environment (or perhaps the entire company).

This post is based on an original recipe by Klayton Monroe.
