---
layout: post
published: true
title: ! 'Troubleshooting PHP Sqlite Query Error: Unable to open database'
permalink: /troubleshooting-sqlite-query-error-unable-to-open-database/
wordpress_id: 361
categories:
- Links
- Linux
- PHP
- Web Server
- web server user
- php sqlite unable to open database file
- sqlite file is encrypted or is not a database
---


<img align="right" id="image360" src="http://lh5.ggpht.com/-oYnb2co2raA/UVl9vOpj-4I/AAAAAAAAFmo/JHXzHcowQbY/sqlite.png" alt="Sqlite Logo" />If you are using <a href="http://www.php.net/">PHP</a> and are going to send INSERT or UPDATE queries or any other query resulting in a IO write, you will need to make the folder that contain your <a href="http://www.sqlite.org/">Sqlite</a> database e.g. "file.db" writable by the web server user, otherwise you'll receive error message - "Unable to open database . . . ". File permissions are not enough
