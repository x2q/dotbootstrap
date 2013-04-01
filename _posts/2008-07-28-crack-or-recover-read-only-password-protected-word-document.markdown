---
layout: post
published: true
title: Crack or Recover Read-only Password Protected Word Document
permalink: /crack-or-recover-read-only-password-protected-word-document/
wordpress_id: 652
categories:
- News
- Crack
- Microsoft
- Excel
- hack
- xp
- office
- word
- doc
- recover
- password
- html
- HTML-Code using Microsoft Script Editor
- Microsoft Script Editor
- then search
- crack docx password
- doc crack
- crack protected word document
- crack doc
- crack docx
---


From time to time someone sends me read-only password protected Microsoft Word (doc-files) documents. Getting word files is in it self is bothersome, but that's the way the world of IT is today, but hopefully more and more home and business users discover the <a href="http://www.openoffice.org/">OpenOffice productivity suite</a> in the future. But getting read-only password protected word files is just incredibly annoying - first of all it tells you that the person that just sent you the document doesn't have a clue on security matters, since protection techniques of that type is of no real use. They are simply too easy to crack, but again - why at all protect a document...

<strong>Howto crack and get rid of the "protection" / "Recover" the document ;)</strong>
If you are using Microsoft Office XP or Microsoft Office 2003, you can change the view to HTML-Code using Microsoft Script Editor by pressing the Alt+Shift+F11 keys.

When the document is opened in the Microsoft Script Editor then search for "Password" and you will find something similar to this:
  <w :DocumentProtection>Forms</w>
  <w :DocumentProtection>ReadOnly</w>
  <w :UnprotectPassword>FED5E3B6</w>

<strong>To remove the document's form protection:</strong>
 - remove the line containing <strong>Forms</strong> and then save the document using Ctrl+s, the form protection should then be gone.



<strong>To remove the document's read-only protection:</strong>
 - remove the line containing <strong>ReadOnly</strong> and then save the document using Ctrl+s, the read-only protection should then be gone.

<strong>To remove the password:</strong>
  - remove the line containing the password and then save the document using Ctrl+s.

This <a href="http://howtotroubleshoot.blogspot.com/2007/09/unprotect-protected-word-docs.html">blog entry</a> describes this and other techniques to recover password protected office documents and so does this <a href="http://www.gmayor.com/Remove_Password.htm">page</a>.
