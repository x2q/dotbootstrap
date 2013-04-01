---
layout: post
published: true
title: Howto Create Generate a Certificate Signing Request
permalink: /howto-create-generate-a-certificate-signing-request/
wordpress_id: 494
categories:
- Links
- News
- Linux
- apache
- Open Source
- Debian
- Ubuntu
- security
- openSSL
- x509
- certificates
- private key
- openssl certificate signing request
- debian generate csr
- linux generate csr
- nokia certificate generator
- nokia certificate maker
- generate csr linux
---


This howto describes the instructions to generate a <a href="http://en.wikipedia.org/wiki/Certificate_signing_request">CSR</a> for your Web site. When you have completed the outlined steps. In this guide I use <a href="http://en.wikipedia.org/wiki/OpenSSL">OpenSSL</a>, which is the open source project that replaced <a href="http://en.wikipedia.org/wiki/SSLeay">SSLeay</a>.

Create a <a href="http://en.wikipedia.org/wiki/Private_key">RSA private key</a> for your Apache server, <a href="http://en.wikipedia.org/wiki/Privacy_Enhanced_Mail">PEM</a>-formatted:

```

openssl genrsa -out domain.com.key 1024

```



Create a Certificate Signing Request using the <a href="http://en.wikipedia.org/wiki/Private_key">RSA private key</a> created above (output will be <a href="http://en.wikipedia.org/wiki/Privacy_Enhanced_Mail">PEM format</a>):

```

openssl req -new -key domain.com.key -out domain.com.csr

```


Note that the Common Name field is the field where the domain name should be stated.
