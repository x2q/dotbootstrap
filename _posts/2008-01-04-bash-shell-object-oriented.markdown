---
layout: post
published: true
title: ! 'Bash Shell: Object Oriented'
permalink: /bash-shell-object-oriented/
wordpress_id: 561
categories:
- Links
- Linux
- Usability
- Open Standards
- Open Source
- Vista
- Debian
- Ubuntu
- Fedora
- Windows Vista
- operating system
- alias function.edit='$EDITOR
- alias file.head='head
- object oriented bash
- bash object oriented
- bash objects
- bash object
- object oriented shell
---


Object orientation is getting a more and more popular paradigm - and MS has tried to create a object oriented shell for the <a href="http://en.wikipedia.org/wiki/Microsoft_Windows">Windows Vista operating system</a>. However a traditional <a href="http://en.wikipedia.org/wiki/Bash">BASH-shell</a> can also be scripted to mimic <a href="http://en.wikipedia.org/wiki/Object-oriented_programming">object orientation</a> using a number of aliases - listed here bellow.


```

    # object-oriented-like behaviour 
    alias alias.delete='unalias' 
    alias alias.edit='$EDITOR ~/.aliases.bash' 
    alias alias.list='alias' 
    alias alias.list.terse='alias.list | cut -d " " -f 2- | cut -d "=" -f1' 
    alias alias.new='alias' 
    alias alias.reload='. ~/.aliases.bash' 
    alias alias.save='alias > ~/.aliases.bash' 

    alias dir.change='cd' 
    alias dir.contents='ls' 
    alias dir.contents.long='dir.contents -la' 
    alias dir.current='pwd' 
    alias dir.delete='rmdir' 
    alias dir.list='ls' 
    alias dir.list.help='ls --help' 
    alias dir.move='mv' 
    alias dir.new='mkdir' 
    alias dir.remove='rmdir' 
    alias dir.rename='mv' 
    alias dir.stat='stat' 
    alias dir.properties='stat' 

    alias sys.date='date' 
    alias sys.system='uname' 

    alias file.contents='cat' 
    alias file.contents.backwards='tac' 
    alias file.contents.pager='less' 
    alias file.contents.reverse='rev' 
    alias file.cut='cut' 
    alias file.delete='rm' 
    alias file.head='head' 
    alias file.grep='grep' 
    alias file.join='join' 
    alias file.move='mv' 
    alias file.new='touch' 
    alias file.paste='paste' 
    alias file.properties='stat' 
    alias file.rename='mv' 
    alias file.sort='sort' 
    alias file.stat='stat' 
    alias file.tail='tail' 
    alias file.type='file' 

    alias function.delete='unset -f' 
    alias function.edit='$EDITOR ~/.functions.bash' 
    alias function.list.detailed='declare -f' 
    alias function.list.terse='declare -F | cut -d "=" -f2- ' 
    alias function.new='function' 
    alias function.reload='. ~/.functions.bash' 
    alias function.save='declare -f > ~/.functions.bash ' 

    alias user.delete='userdel' 
    alias user.id='id' 
    alias user.list='sort /etc/passwd' 
    alias user.me='whoami' 
    alias user.new='useradd' 
    alias user.properties='id' 
    alias user.stat='id' 

    alias variable.delete='unset' 
    alias variable.exported.list='declare -x' 
    alias variable.list='set' 
    alias variable.new='declare' 

```
