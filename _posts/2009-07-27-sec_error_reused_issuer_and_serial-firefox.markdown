---
layout: post
published: true
title: sec_error_reused_issuer_and_serial - Firefox
permalink: /sec_error_reused_issuer_and_serial-firefox/
wordpress_id: 815
categories:
- News
- Firefox
- x509
- California
- correspondent
- server administrator
- web site owners
- particular site
- sec_error_reused_issuer_and_serial
- ! 'Error code: sec_error_reused_issuer_and_serial'
- firefox sec_error_reused_issuer_and_serial
- sec_error_reused_issuer_and_serial firefox
---


<strong>Secure Connection Failed</strong>
 
An error occurred during a connection to 192.168.12.122.

You have received an invalid certificate.  Please contact the server administrator or email correspondent and give them the following information:

Your certificate contains the same serial number as another certificate issued by the certificate authority.  Please get a new certificate containing a unique serial number.

(Error code: sec_error_reused_issuer_and_serial)

        
The page you are trying to view can not be shown because the authenticity of the received data could not be verified.

    * Please contact the web site owners to inform them of this problem.



<strong>Solution</strong>
If you have recieved this error and are trying to access something that has a self signed certificate, there are two places in Firefox that you must visit in order to access the particular site again.

The first visit Tools--> options-->Advanced-->View Certificates

You must remove the certificates in the "Servers" tab, then under the same location you must remove the certificate authority because it is a self signed certificate, so on the "Authorities" tab, simply find the CA for the device you are having trouble with and delete it.
