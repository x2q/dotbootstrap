---
layout: post
published: true
title: ! 'SSL: Verifying that a Certificate matches a Private Key'
permalink: /ssl-verifying-that-a-certificate-matches-a-private-key/
wordpress_id: 790
categories:
- News
- Linux
- Open Standards
- apache
- Open Source
- Debian
- Ubuntu
- Fedora
- security
- openSSL
- x509
- certificates
- ssl
- private key
- Public Key
- no certificate matches private key
- openssl No certificate matches private key
---


The private key contains a series of numbers. Two of those numbers form the "public key", the others are part of your "private key". The "public key" bits are also embedded in your Certificate (we get them from your CSR). To check that the public key in your cert matches the public portion of your private key, you need to view the cert and the key and compare the numbers.

Normally it requires some manual number matching to match a given private key with a given certificate, however with this command you are able to do a comparison automatic:


```

$ (openssl x509 -noout -modulus -in server.pem | openssl md5 ;\
   openssl rsa -noout -modulus -in server.key | openssl md5) | uniq

```


(If more than one hash is displayed, they don't match)
