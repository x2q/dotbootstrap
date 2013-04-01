---
layout: post
published: true
title: ! 'Ubuntu Howto: Install Ruby and Ruby on Rails'
permalink: /ubuntu-howto-install-ruby-and-ruby-on-rails/
wordpress_id: 521
categories:
- Links
- Linux
- Ruby on Rails
- Ruby
- Webdesign
- Open Source
- Debian
- Ubuntu
- standard Ruby package manager
- ruby on rails ubuntu 9 10
- install ruby ubuntu 9
- ubuntu rails path
---



<img align="right" id="image323" src="http://lh6.ggpht.com/-Fy6uSzz0rOU/UVl_Yz0JVNI/AAAAAAAAFvg/KsV_z9cYulU/rails.png" alt="Ruby on Rails" />

To install Ruby and RubyGems - the standard Ruby package manager:

```

cc@ubuntu:~$ sudo apt-get install ruby rubygems

```


then install Ruby on Rails using RubyGems:

```

cc@ubuntu:~$ sudo gem install rails --include-dependencies

```


or using apt-get (aptitude)

```

cc@ubuntu:~$ sudo apt-get install rails

```



and then create a new rails application:

```

cc@ubuntu:~$ rails path/to/your/new/application
cc@ubuntu:~$ cd path/to/your/new/application
cc@ubuntu:~$ ruby script/server

```


Check that everything works by pointing your browser to http://0.0.0.0:3000
