---
layout: post
published: true
title: TCP Resource Exhaustion Denial of Service (DoS) Attack
permalink: /tcp-resource-exhaustion-denial-of-service-dos-attack/
wordpress_id: 667
categories:
- News
- nmap
- DoS
- tcp
- Outpost24
- DNS
- Web Server
- TCP/IP protocol
- mail server
- IP
- Jack Louis
- Robert Lee
- Dan Kaminsky
- Finland
- Internet protocol flaw
- media circus
- Internet communication
- backtrack ddos
---



<a href="http://insecure.org/">Outpost24's TCP DOS Attack Explained</a><br /><blockquote>Explaining the &acirc;&euro;&oelig;New&acirc;&euro; TCP Resource Exhaustion Denial of Service (DoS) Attack by Fyodor, October 2, 2008<br /><br />Introduction<br /><br />Robert Lee and Jack Louis recently went public claiming to have discovered a new and devastating denial of service (DoS) vulnerability in the core TCP/IP protocol stack used for almost all Internet communication. They refuse to release details before their talk at the T2 security conference in Finland on October 17. Yet they have given many alarming interviews, and the press is having a field day spreading fear and uncertainty. Articles have appeared on The Register (&acirc;&euro;&oelig;DoS attack reveals (yet another) crack in net's core&acirc;&euro;), Slashdot (&acirc;&euro;&oelig;New Denial-of-Service Attack is a Killer&acirc;&euro;), Search Security (&acirc;&euro;&oelig;TCP is fundamentally borked&acirc;&euro;), and many more publications. In the Register article, Robert Lee says &acirc;&euro;&oelig;We haven't found anybody who has a TCP stack that runs TCP based services that isn't vulnerable&acirc;&euro; and that a target machine &acirc;&euro;&oelig;basically self thrashes, and the only recovery after about two to four minutes worth of attack flow, even after the attack stops, is to reboot the machine&acirc;&euro;. The SearchSecurity article ends with this chilling paragraph:<br /><br />    &acirc;&euro;&oelig;The best advice I have right now is don't allow anonymous connections. Make whitelist so only certain IP addresses can come in,&acirc;&euro; Lee said, acknowledging the impracticality of that for a Web server or mail server or virtually any other TCP-enabled device. &acirc;&euro;&oelig;There's no real workaround right now.&acirc;&euro; <br /><br />While I know and respect these researchers, I've had enough of the recent spate of people announcing (supposedly) massive security vulnerabilities, then refusing to back up their claims with details until a talk weeks or months away. Obviously Dan Kaminsky ignited this recent trend with his DNS flaw. While many of the researchers are earnest and call this &acirc;&euro;&oelig;responsible disclosure&acirc;&euro;, it often reeks like a PR campaign. When you tell the press that you've discovered a core Internet protocol flaw so severe that you can't even provide any details for fear that the entire network could come crashing down, they just eat that up and it devolves into a media circus.<br /><br />I don't presume to tell people how to report vulnerabilities&acirc;&euro;&rdquo;disclosure has long been one of the most personal and political issues in the security community. So I let them decide for themselves. But I don't need to keep quiet if I figure out or independently discover an issue. And I suspect that I've nailed this one. I recognize their vague description of the attack and results because I've written and used a similar DoS tool. I was not the first to do so, either. </blockquote>
