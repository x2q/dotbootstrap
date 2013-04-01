---
layout: post
published: true
title: ! 'Dalvik: How Google routed around Sun''s IP-based licensing restrictions
  on Java ME'
permalink: /dalvik-how-google-routed-around-suns-ip-based-licensing-restrictions-on-java-me/
wordpress_id: 555
categories:
- Links
- News
- Linux
- Usability
- Open Standards
- Design
- Open Source
- Nokia
- Java
- user experience
- Microsoft
- google
- Virtual Machine
- Java bytecode
- Android
---




<blockquote>
[...] Google released the Android code and I took a serious look at its internals... and found the solution for the licensing problem. It's called Dalvik and it's the new name of Sun's worst nightmares.

Dalvik is a virtual machine, just like Java's or .NET's.. but it's Google's own and they're making it open source without having to ask permission to anyone (well, for now, in the future expect a shit-load of IP-related lawsuits on this, especially since Sun and Microsoft signed a cross-IP licensing agreement on exactly such virtual machines technologies years ago


[...]

Android uses the syntax of the Java platform (the Java "language", if you wish, which is enough to make java programmers feel at home and IDEs to support the editing smoothly) and the java SE class library but not the Java bytecode or the Java virtual machine to execute it on the phone. [...]

The trick is that Google doesn't claim that Android is a Java platform, although it can run some programs written with the Java language and against some derived version of the Java class library. Sun could prevent this if they had a patent on the standard class library, but they don't and, even if they did, I strongly doubt it would be enforceable since Android doesn't claim to be compatible (and in fact, could very well claim that their subset/superset is an innovation on the existing patent and challenge Sun's position).

[...]


Not only this allows Google to avoid having to battle thru the JCP for any change to the Java ME "standard" or tolerate Sun's unique ability to veto any JCP change, but gives users a much more 'fresh' and modern class library to play with and built-in hooks to all the hardware features of your phone, including things like OpenGL, bluetooth, USB and all those things, which don't come with the standard Java ME and therefore cannot be taken for granted by the developers.

</blockquote>






<a href="http://www.betaversion.org/~stefano/linotype/news/110/">Dalvik: How Google routed around Sun's IP-based licensing restrictions on Java ME</a>


