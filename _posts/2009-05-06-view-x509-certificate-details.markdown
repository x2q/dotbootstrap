---
layout: post
published: true
title: View x509 certificate details
permalink: /view-x509-certificate-details/
wordpress_id: 792
categories:
- News
- Linux
- Open Standards
- apache
- Open Source
- Debian
- Ubuntu
- Fedora
- Firefox
- openSSL
- ssl
- openssl view certificate
- openssl show certificate
- openssl show certificate information
- openssl show certificate details
- openssl show certificate info
---


OpenSSL is quite a complex application, however it is quite easy to get it to show you details or a given x509 SSL certificate using this command:


```

$ openssl x509 -in filename.crt -noout -text

```


Where filename corresponds to the X.509 certificate file, which typically would end in .crt, .cert or .pem.
