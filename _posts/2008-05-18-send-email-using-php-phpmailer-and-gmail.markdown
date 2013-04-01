---
layout: post
published: true
title: Send Email using PHP, PHPMailer and Gmail
permalink: /send-email-using-php-phpmailer-and-gmail/
wordpress_id: 619
categories:
- News
- PHP
- gmail
- ssl
- PHPMailer
- SMTP
- mail server
- phpmailer gmail
- PHP Gmail
- php send mail gmail
- phpmailer sendmail
- phpmailer smtp ssl
---


This short guide explains how to use gmail as mail server using PHP and PHPMailer.

<strong>Download PHPMailer</strong>
Download PHPMailer from <a href="http://phpmailer.worxware.com/">http://phpmailer.sourceforge.net</a> - <a href="http://sourceforge.net/projects/phpmailer/files/">direct link</a>.

<strong>Extract and upload</strong>
Extract the PHPMailer-packages to a folder named phpmailer2 or any other folder name. Afterwards upload the folder to a <a href="http://php.net/">PHP-enabled</a> webserver.

<strong>Implement into code</strong>
Implement the PHPMailer function into the existing E-Mail-code as shown in the included examples.

<strong>Gmail specific settings</strong>
The following settings are needed in order to use Gmail as mail-hub and SMTP server.

<pre name="code" class="php">
$mail->Mailer = "smtp";
$mail->Host = "ssl://smtp.gmail.com";
$mail->Port = 465;
$mail->SMTPAuth = true; // turn on SMTP authentication
$mail->Username = "username@gmail.com"; // SMTP username
$mail->Password = "password"; // SMTP password

```


<strong>My experience using Gmail as SMTP server</strong>
So far I haven't got any problems. Their service is always online and available, which is quite opposite to what I have experienced with my low budget hosting provider so far.
