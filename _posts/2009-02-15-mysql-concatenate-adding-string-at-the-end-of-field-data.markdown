---
layout: post
published: true
title: ! 'MySQL Concatenate: Adding String At The End Of Field Data'
permalink: /mysql-concatenate-adding-string-at-the-end-of-field-data/
wordpress_id: 754
categories:
- News
- MySQL
- sql
- mysql concatenate strings
- mysql update concat
- mysql merge strings
- mysql concatenate
- mysql append string
- mysql merge string
---


From time to time it is useful to be able to append a string or data to an existing data of a data field by using concat function in MySQL.

For example we want to add site signature at the end of the comments posted by users.

concat(field_name,&rdquo;string to add&rdquo;)

Now let us see how it is used in a MySQL table query.

update comments set field_name=concat(field_name,'string to add') where id='1';
