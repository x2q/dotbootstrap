---
layout: post
published: true
title: Openssl to create an unencrypted key from an encrypted one (Remove password)
permalink: /openssl-to-create-an-unencrypted-key-from-an-encrypted-one-remove-password/
wordpress_id: 280
categories:
- News
- Linux
- Open Standards
- apache
- openSSL
- encryption
- ssl
- private key
- openssl remove password from key
- openssl remove password
- openssl remove key password
- openssl key remove password
- openssl remove password key
---
<strong>Remove the encryption from the RSA private key</strong>

```

debian21:~# openssl rsa -in server.key -out server.key.unencrypted

```


<strong>Then make sure the server.key.unencrypted file is only readable by root</strong>

```

debian21:~# chmod 400 server.key.unencryped

```


Now server.key.unencrypted will contain an unencrypted copy of the key. If you point your server (e.g. Apache ) at this file it will not prompt you for a pass-phrase.


<a href="http://www.openssl.org/">Link to OpenSSL - The Open Source toolkit for SSL/TLS</a>

