---
layout: post
published: true
title: Apache2 deflate setup
permalink: /apache2-deflate-setup/
wordpress_id: 85
categories:
- News
- xml
- html
- apache2 deflate
- apache deflate css
- apache deflate javascript
- apache deflate
- deflate css
- apache deflate js
---



```

# mod_deflate setup
<location />
    <ifmodule mod_deflate.c>
    # compress content with type html, text, and css
    AddOutputFilterByType DEFLATE text/html text/plain text/xml text/css text/javascript application/x-javascript
    #<ifmodule mod_headers.c>
      # properly handle requests coming from behind proxies
    #  Header append Vary User-Agent
    #</ifmodule>
  </ifmodule>
</location>

```


Could properly reduce normal pages, javascripts, stylesheets by 2/3.
