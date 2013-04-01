---
layout: post
published: true
title: Mysql Data Import
permalink: /mysql-data-import/
wordpress_id: 364
categories:
- Links
- Linux
- Mysql Data Import
---



```
mysql> LOAD DATA LOCAL INFILE 'adresser.txt' INTO TABLE AccessAddress FIELDS TERMINATED BY ';' OPTIONALLY ENCLOSED BY '"' IGNORE 1 LINES (@dummy, MunicipalityCode, StreetCode, @dummy, StreetBuildingIdentifier, PostCodeIdentifier, @dummy, @dummy, @dummy, @dummy, Easting, Northing);
Query OK, 249972 rows affected, 65535 warnings (2.55 sec)
Records: 249972  Deleted: 0  Skipped: 0  Warnings: 249972

```




```
mysql> LOAD DATA LOCAL INFILE 'vejnavn.txt' INTO TABLE Street FIELDS TERMINATED BY ';' OPTIONALLY ENCLOSED BY '"' IGNORE 1 LINES (MunicipalityCode, StreetCode, StreetName);                                                                         Query OK, 13925 rows affected, 13926 warnings (0.06 sec)
Records: 13925  Deleted: 0  Skipped: 0  Warnings: 13925

```


