---
layout: post
published: true
title: Convert Northing and Easting UTM to Longitude and Latitude
permalink: /convert-northing-and-easting-utm-to-longitude-and-latitude/
wordpress_id: 348
categories:
- News
- PHP
- programming
- Danmark
- USD
- convert northing easting to latitude longitude
- northing and easting to latitude and longitude
- convert easting northing to lat long
- convert northing and easting to latitude and longitude
- easting northing latitude longitude
- convert eastings and northings to latitude and longitude
---


<code lang="php">
< ?php
// Titken Lipinski, 2007

function LatLonPointUTMtoLL($f, $f1, $j=32) {
    // $f = Northing
    // $f1 = Easting
    // $j: UTM ZONE (Danmark = 32)

    $d = 0.99960000000000004; // scale along long0
    $d1 = 6378137; // Polar Radius
    $d2 = 0.0066943799999999998;

    $d4 = (1 - sqrt(1 - $d2)) / (1 + sqrt(1 - $d2));
    $d15 = $f1 - 500000;
    $d16 = $f;
    $d11 = (($j - 1) * 6 - 180) + 3;
    $d3 = $d2 / (1 - $d2);
    $d10 = $d16 / $d;
    $d12 = $d10 / ($d1 * (1 - $d2 / 4 - (3 * $d2 * $d2) / 64 - (5 * pow($d2,3) ) / 256));
    $d14 = $d12 + ((3 * $d4) / 2 - (27 * pow($d4,3) ) / 32) * sin(2 * $d12) + ((21 * $d4 * $d4) / 16 - (55 * pow($d4,4) ) / 32) * sin(4 * $d12) + ((151 * pow($d4,3) ) / 96) * sin(6 * $d12);
    $d13 = rad2deg($d14);
    $d5 = $d1 / sqrt(1 - $d2 * sin($d14) * sin($d14));
    $d6 = tan($d14) * tan($d14);    
    $d7 = $d3 * cos($d14) * cos($d14);
    $d8 = ($d1 * (1 - $d2)) / pow(1 - $d2 * sin($d14) * sin($d14), 1.5);    
    $d9 = $d15 / ($d5 * $d);
    $d17 = $d14 - (($d5 * tan($d14)) / $d8) * ((($d9 * $d9) / 2 - (((5 + 3 * $d6 + 10 * $d7) - 4 * $d7 * $d7 - 9 * $d3) * pow($d9,4) ) / 24) + (((61 + 90 * $d6 + 298 * $d7 + 45 * $d6 * $d6) - 252 * $d3 - 3 * $d7 * $d7) * pow($d9,6) ) / 720);
    $d17 = rad2deg($d17); // Breddegrad (N)
    $d18 = (($d9 - ((1 + 2 * $d6 + $d7) * pow($d9,3) ) / 6) + (((((5 - 2 * $d7) + 28 * $d6) - 3 * $d7 * $d7) + 8 * $d3 + 24 * $d6 * $d6) * pow($d9,5) ) / 120) / cos($d14);
    $d18 = $d11 + rad2deg($d18); // Længdegrad (&Atilde;&tilde;)
    return array('lat'=>$d17,'lng'=>$d18);
}
?>

```
