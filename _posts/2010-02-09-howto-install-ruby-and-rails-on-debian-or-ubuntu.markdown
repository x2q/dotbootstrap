---
layout: post
published: true
title: ! 'Howto: Install Ruby and Rails on Debian or Ubuntu'
permalink: /howto-install-ruby-and-rails-on-debian-or-ubuntu/
wordpress_id: 935
categories:
- News
- Linux
- Ruby on Rails
- Ruby
- Debian
- Ubuntu
- RoR
- apt-get
- etch
- lenny
- deb
- Rails
- rubygems
- gem
- gems
- Debian package
- Web developers
- package manager
- open source web application framework
---


<strong>Ruby on Rails - what the f...</strong>
Ruby on Rails, often shortened to Rails or RoR, is an open source web application framework for the Ruby programming language. It is intended to be used with an Agile development methodology that is used by web developers for rapid development.

Ruby on Rails is often installed using RubyGems, a package manager, which is included with Ruby. Many Linux distributions also support installation of Rails and its dependencies through their native package management system, anyway no matter the installation technique, installing Ruby on Rails on a Debian or Ubuntu distribution is plain sailing and very easy.

<strong>Installing Ruby on Rails using RubyGems</strong>

<strong>Install Ruby and RubyGems</strong>

```

sudo aptitude install ruby rubygems

```


<em>As I wrote this post, there was a nasty bug in the Rails dependency notation for Rack, which means you'll need to install version 1.0.1 of Rack instead of the default version, which is as of now version 1.1.0. </em> 

<strong>Install Rails</strong>

```

sudo gem install rack --version 1.0.1
sudo gem install rails

```


That's all. You are done.


<strong>Installing Ruby on Rails using apt-get or aptitude</strong>

<strong>Install Ruby on Rails</strong>

```

sudo aptitude install rails

```


That's all. You are done.
