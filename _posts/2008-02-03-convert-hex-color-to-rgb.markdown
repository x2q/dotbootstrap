---
layout: post
published: true
title: Convert Hex Color to RGB
permalink: /convert-hex-color-to-rgb/
wordpress_id: 593
categories:
- News
- Usability
- Webdesign
- Design
- themes
- user experience
- colors
- tool
- hex to ARGB
- as3 hex to rgb
- java convert hex to rgb
---


Converting a <a href="http://en.wikipedia.org/wiki/Hexadecimal">hex</a> color string (e.g. "AABBCC") into numeric <a href="http://en.wikipedia.org/wiki/RGB_color_model">RGB (Red Green and Blue color model)</a> values (e.g. 170,187,207) of the exact same color is quite simple. Here below i have craeted a  small tool to perform to actual color conversion.

<script type="text/javascript">
R = HexToR("#FFFFFF");
G = HexToG("#FFFFFF");
B = HexToB("#FFFFFF");
function HexToR(h) { return parseInt((cutHex(h)).substring(0,2),16) }
function HexToG(h) { return parseInt((cutHex(h)).substring(2,4),16) }
function HexToB(h) { return parseInt((cutHex(h)).substring(4,6),16) }
function cutHex(h) { return (h.charAt(0)=="#") ? h.substring(1,7) : h}
</script>

<form name=rgb>
<input type=text name=hex size=8 value="FFFFFF"/>
<input type=button name=btn value="Convert to RGB" onCLick="this.form.r.value=HexToR(this.form.hex.value); 
this.form.g.value=HexToG(this.form.hex.value); this.form.b.value=HexToB(this.form.hex.value);"/>


R:<input type=text name=r size=3/>


G:<input type=text name=g size=3/>


B:<input type=text name=b size=3/>
</form>


Use <a href="http://www.javascripter.net/faq/rgbtohex.htm">this converter to convert a set of RGB color codes into hex</a>.
