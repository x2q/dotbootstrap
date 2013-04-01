---
layout: post
published: true
title: ! 'PHP Professional Tip #1 - Type Hinting'
permalink: /php-professional-tip-1-type-hinting/
wordpress_id: 488
categories:
- Links
- News
- PHP
- programming
- php type hinting
- type hinting php
---


<a href="http://php.net/">PHP</a> 5.1 introduced Type Hinting. Type Hinting means that functions are able to force parameters to be objects, by specifying the name of the class in the function prototype. It it also possible to specify that a certain parameters should be an array. Unfortunately the primitives types; string, int etc isn't supported in <a href="http://php.net/">PHP</a> 5.1.

Type hinting code example.
<code lang="php">
// An example class
class MyClass
{
    /**
     * A test function
     *
     * First parameter must be an object of type OtherClass
     */
    public function test(OtherClass $otherclass) {
        echo $otherclass->var;
    }


    /**
     * Another test function
     *
     * First parameter must be an array
     */
    public function test_array(array $input_array) {
        print_r($input_array);
    }
}

// Another example class
class OtherClass {
    public $var = 'Hello World';
}

```


Consult the PHP Manual for more examples on <a href="http://ca.php.net/manual/en/language.oop5.typehinting.php">PHP type hinting</a>
