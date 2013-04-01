---
layout: post
published: true
title: MDB Tools to export (migrate) from mdb (Microsoft Access format) to MySQL
permalink: /mdb-tools-to-export-migrate-from-mdb-microsoft-access-format-to-mysql/
wordpress_id: 288
categories:
- Links
- Linux
- Open Source
- Microsoft
- MySQL
- Oracle
- databases
- PostgreSQL
- Microsoft SQL Server
- IBM DB2
- Microsoft Access
- mdb-export
- mdbtools windows
- export mdb to mysql
- MDBTools tutorial
- mdbtools howto
---
Today I was working on how to convert an old <a href="http://en.wikipedia.org/wiki/Microsoft_access">Microsoft Access</a> database into a <a href="http://en.wikipedia.org/wiki/Mysql">MySQL database</a>. This convertion could be obtained by first converting the tables in the mdb-file into <a href="http://en.wikipedia.org/wiki/Comma-separated_values">CSV-files (Comma Separated Values)</a> using <a href="http://mdbtools.sourceforge.net/">MDB Tools</a> and then by importing the csv-files into <a href="http://en.wikipedia.org/wiki/Mysql">MySQL</a> using <a href="http://en.wikipedia.org/wiki/Phpmyadmin">phpMyAdmin</a>.

To export a given table from a mdb-file, we type:

```

mdb-export db.mdb customers >> customers.csv

```


In my case, since I got some danish characters, I need to force mdbtools to encode everything as <a href="http://en.wikipedia.org/wiki/ISO8859-1">ISO8859-1</a> instead of <a href="http://en.wikipedia.org/wiki/UTF-8">UTF-8</a>, which is the default. This can be done by setting the environment variable MDB_ICONV to <a href="http://en.wikipedia.org/wiki/ISO8859-1">ISO8859-1</a>

```

export MDB_ICONV="ISO8859-1"

```


The resulting CSV-files coult be imported into <a href="http://en.wikipedia.org/wiki/Mysql">MySQL</a> using <a href="http://en.wikipedia.org/wiki/Phpmyadmin">phpMyAdmin</a>.

<img id="image287" src="http://lh3.ggpht.com/--kasB8f6h4s/UVl9Y-E2jxI/AAAAAAAAFkI/7NN6BIMlxZk/200px-mysql.svg.png" alt="MySQL Logo" />



Another howto on database migration <a href="http://edoceo.com/creo/ms2pg">ms2pg - Migrate Microsoft SQL Server Database to PostgreSQL Database</a>.
