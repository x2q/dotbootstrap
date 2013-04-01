---
layout: post
published: true
title: ! 'vtiger CRM Webservices: Create New Leads Using PHP-SOAP'
permalink: /vtiger-crm-webservices-create-new-leads-using-php-soap/
wordpress_id: 389
categories:
- Links
- Linux
- Open Standards
- SOA
- PHP
- CRM
- vtiger soap
- vtiger webservice
- vtiger web services
- vtiger web service
- vtiger webservices
---
The <a href="https://www.vtiger.com/crm/">vtiger CRM</a> has a number of Webservices that can be accessed through SOAP. The original examples from <a href="https://www.vtiger.com/crm/">vtiger</a> for accessing the services are implemented using <a href="http://sourceforge.net/projects/nusoap/">NuSOAP</a>. Here I have created an example using the built-in <a href="http://dk.php.net/SOAP">PHP SOAP implementation</a>. 

<code lang="PHP">
< ?php
$client = new SoapClient(
"http://crm.vtigersite.com/vtigerservice.php?service=webforms&wsdl",
 array(
"location" => "http://crm.vtigersite.com/vtigerservice.php?service=webforms",
"compression" => SOAP_COMPRESSION_ACCEPT | SOAP_COMPRESSION_GZIP,
"login" => "admin", // default
"password" => "admin" // default
));

$params = array();
$params["lastname"] = "lastnamea";
$params["email"] = "email@email.com";
$params["phone"] = "phone";
$params["company"] = "company";
$params["country"] = "country";
$params["description"] = "description";

// user id to assign the lead in vtiger
$params["assigned_user_id"] = 1;

$result = $client->__soapCall("create_lead_from_webform", $params);
echo $result;
?>

```



