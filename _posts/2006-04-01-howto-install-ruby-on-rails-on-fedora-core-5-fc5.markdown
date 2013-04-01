---
layout: post
published: true
title: Howto install Ruby on Rails on Fedora Core 5 (fc5)
permalink: /howto-install-ruby-on-rails-on-fedora-core-5-fc5/
wordpress_id: 236
categories:
- News
- Ruby on Rails
- package manager
- Fedora Core 5
---
<strong>First we'll need to install the Ruby packages:</strong>

```

sudo yum install ruby ruby-devel ruby-libs irb rdoc

```


<strong>Then download and install RubyGems ( a package manager - like apt-get just for Ruby packages):</strong>

```

wget http://rubyforge.org/frs/download.php/5207/rubygems-0.8.11.tgz
tar xzvf rubygems-0.8.11.tgz
cd rubygems-0.8.11
sudo ruby setup.rb

```

<strong>Then we are ready to install Ruby on Rails by using RubyGems:</strong>

```

sudo gem install rails --include-dependencies

```

<strong>Create a application skeleton:</strong>

```

rails path/to/your/new/application
cd path/to/your/new/application
ruby script/server

```

<strong>Now launch a webbrowser and point it to http://0.0.0.0:3000/</strong>

<a title="Ruby on Rails on FC5" onclick="doPopup(235);return false;" class="imagelink" href="http://lh6.ggpht.com/-CJGQTVx35w0/UVl8_0hR7yI/AAAAAAAAFhc/_5-4VYd6Wlo/screenshot.png">
<img width="93" height="96" alt="Ruby on Rails on FC5" id="image235" src="http://lh5.ggpht.com/-ChsRyffXv3E/UVl8-Wm6PaI/AAAAAAAAFhY/xV8H7GjUaYI/screenshot.thumbnail.png" /></a>

