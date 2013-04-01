---
layout: post
published: true
title: Howto setup SPF (Sender Policy Framework) on a domain
permalink: /howto-setup-spf-sender-policy-framework-on-a-domain/
wordpress_id: 273
categories:
- Links
- News
- Open Standards
- DNS
- online tool
- SPF howto
- spf record generator
- spf generator
- postfix spf howto
---
<a href="http://en.wikipedia.org/wiki/Sender_Policy_Framework">SPF is a Policy Framwork</a> that helps fighting return-path address forgery and makes it easier to identify spoofs. Domain owners identify and pinpoint sending mail servers in a DNS record, and thereby its posible for SMTP receivers (e.g. <a href="http://en.wikipedia.org/wiki/Mail_transfer_agent">MTA</a>s like <a href="http://www.exim.org/">Exim</a>, <a href="http://www.postfix.org/">Postfix</a>, <a href="http://en.wikipedia.org/wiki/Qmail">Qmail</a> etc.) to verify the envelope sender address against this information, and can distinguish authentic messages from forgeries before any message data is transmitted.

<img id="image272" src="http://lh5.ggpht.com/-N2MGTpU_nZU/UVl9TCyf_jI/AAAAAAAAFjg/LATp10BeuG0/protectedbyspf-16.png" alt="SPF Logo" />

<strong>Create a SPF record</strong>
The easist way to create a SPF record is to use this online tool: <a href="http://www.openspf.org/Tools#wizard?mydomain=">http://www.openspf.org/wizard.html?mydomain=</a>

<strong>Deploy the SPF record</strong>
To use the newly created SPF record on a domain, make sure you have access to create a TXT-DNS record for the given domain. If you have access to create a TXT-DNS record all you need is to create such a TXT-DNS record containing the SPF record information, and you are done.


