---
layout: post
published: true
title: Howto Install Ruby and Ruby on Rails on Debian Etch 4.0
permalink: /howto-install-ruby-and-ruby-on-rails-on-debian-etch-40/
wordpress_id: 324
categories:
- Links
- Linux
- Ruby on Rails
- Ruby
- AJAX
- Webdesign
- Open Source
- Debian
- Ubuntu
- standard Ruby package manager
---




<img align="right" id="image323" src="http://lh6.ggpht.com/-jvDqBWwu2ko/UVl9j3t11HI/AAAAAAAAFlY/ivsgr_8n_DA/rails.png" alt="Ruby on Rails" />

To install Ruby and RubyGems - the standard Ruby package manager:

```

cc@debian23:~$ sudo apt-get install ruby rubygems

```


then install Ruby on Rails using RubyGems:

```

cc@debian23:~$ sudo gem install rails --include-dependencies

```


and then create a new rails application:

```

cc@debian23:~$ rails path/to/your/new/application
cc@debian23:~$ cd path/to/your/new/application
cc@debian23:~$ ruby script/server

```


Check that everything works by pointing your browser to http://0.0.0.0:3000





