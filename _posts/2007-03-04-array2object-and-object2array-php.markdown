---
layout: post
published: true
title: array2object and object2array (PHP)
permalink: /array2object-and-object2array-php/
wordpress_id: 365
categories:
- Links
- News
- PHP
- programming
- php object2array
- object2array
- object2array php
---


<a href="http://www.jonasjohn.de/snippets/">array2object and object2array (PHP)</a>

<code lang=php>
< ?php

/*
** Function: array2object and object2array (PHP)
** Desc: Convert an associative array to an anonymous object and vice versa.
** Example: see below
** Author: Someone of the http://drupaldocs.org/api/4.6/function/array2object developers
*/

function array2object($array) {

    if (is_array($array)) {
        $obj = new StdClass();
        
        foreach ($array as $key => $val){
            $obj->$key = $val;
        }
    }
    else { $obj = $array; }
    
    return $obj;
}

function object2array($object) {
    if (is_object($object)) {
        foreach ($object as $key => $value) {
            $array[$key] = $value;
        }
    }
    else {
        $array = $object;
    }
    return $array;
}


// example:

$array = array('foo' => 'bar', 'one' => 'two', 'three' => 'four');

$obj = array2object($array);

print $obj->one; // output's "two"

$arr = object2array($obj);

print $arr['foo']; // output's bar
?>



```
