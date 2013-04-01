---
layout: post
published: true
title: SMTP Telnet Session
permalink: /smtp-telnet-session/
wordpress_id: 23
categories:
- News
- telnet smtp session
- smtp telnet session
- smtp session telnet
- smtp telnet
- SMTP TELNET COMMANDS
---



```

<cc @trinitas:/> telnet mail.somedomain.com 25
Trying A.B.C.D...
Connected to A.B.C.D.
Escape character is '^]'.
220 mail.somedomain.com. ESMTP Exim 3.36 #1 Mon, 28 Feb 2005 17:15:33 +0100
helo someotherdomain.com
250 mail.somedomain.com Hello user at someotherdomain.com [E.F.G.H]
mail from: cc@someotherdomain.com
250 <cc @someotherdomain.com> is syntactically correct
rcpt to: recipient@somedomain.com
250 <recipient @somedomain.com> is syntactically correct
data
354 Enter message, ending with "." on a line by itself
Subject:Test Message
This is a test message.
.
250 OK id=1D5ncW-0004Ie-00
quit
221 mail.somedomain.com closing connection
Connection closed by foreign host.
<cc @trinitas:/>
</cc></recipient></cc></cc>
```
