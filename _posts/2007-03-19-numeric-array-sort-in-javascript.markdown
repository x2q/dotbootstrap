---
layout: post
published: true
title: Numeric Array Sort in Javascript
permalink: /numeric-array-sort-in-javascript/
wordpress_id: 369
categories:
- Links
- Uncategorized
- JavaScript
- javascript numeric sort
- javascript sort integer array
---


<code lang="javascript">
function sortASC(a, b){ return (a-b); }
function sortDESC(a, b){ return (b-a); }

integerArray = new Array(1,545,1435,3453,342,441,90);

integerArray.sort( sortASC );
document.write('Ascending: ' + integerArray + '<br />');

integerArray.sort( sortDESC );
document.write('Descending: ' + integerArray + '<br />');

```
