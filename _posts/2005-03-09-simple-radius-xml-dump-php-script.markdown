---
layout: post
published: true
title: Simple RADIUS XML dump PHP script
permalink: /simple-radius-xml-dump-php-script/
wordpress_id: 33
categories:
- News
- PHP
- xml
---



```

< ?php
header("Content-Type: text/xml");

// Etstablish MySQL connection
$db = mysql_connect("localhost", "user" , "password");
mysql_select_db("radius", $db) or die("Unable to select database");

$query = "SELECT * FROM radacct ORDER BY RadAcctId";

// Execute the query
$result = mysql_query($query) or die("Query failed");

// Create XML document
$xmldoc = domxml_new_doc("1.0");
$records = $xmldoc->create_element("records");
$records = $xmldoc->append_child($records);

// Iterate throught the result rows
while($row=mysql_fetch_array($result)){ 
  for($i=0;$i<sizeof ($row)/2;$i++){
   $field_name = mysql_field_name($result, $i);
   
   if ($field_name == "RadAcctId")
   {
	   $record = $xmldoc->create_element("record");
	   $record = $records->append_child($record);
	   $recordAttr = $xmldoc->create_attribute("id", $row[$field_name]);
	   $record = $record->append_child($recordAttr);
   }
   else
   {
	   $record = $records->last_child();
	   $recordData = $xmldoc->create_element($field_name);
	   $recordData = $record->append_child($recordData);
	   $text = $xmldoc->create_text_node($row[$field_name]);
	   $text = $recordData->append_child($text);
   }
 }
}

// Output the XML document
echo $xmldoc->dump_mem(true);

```
