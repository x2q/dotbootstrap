---
layout: post
published: true
title: Debugging Server-side Code through IntelliJ IDEA or Eclipse with BEA Weblogic
  8.1
permalink: /debugging-server-side-code-through-intellij-idea-or-eclipse-with-bea-weblogic-81/
wordpress_id: 601
categories:
- News
- Java
- Tomcat
---


Open the Weblogic Server Console and go into the Servers > the name of the server > Configuration Tab > Remote Start.

Then enter or add the following in the Arguments input field:

```

-Xdebug -Xrunjdwp:server=y,transport=dt_socket,address=8000,suspend=n

```

