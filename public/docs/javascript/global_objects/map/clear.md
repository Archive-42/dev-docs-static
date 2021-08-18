Map.prototype.clear()
=====================

The `clear()` method removes all elements from a `Map` object.

Syntax
------

    clear()

### Return value

[`undefined`](../undefined).

Examples
--------

### Using clear()

    var myMap = new Map();
    myMap.set('bar', 'baz');
    myMap.set(1, 'foo');

    myMap.size;       // 2
    myMap.has('bar'); // true

    myMap.clear();

    myMap.size;       // 0
    myMap.has('bar')  // false

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-map.prototype.clear">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-map.prototype.clear</span></a></td></tr></tbody></table>

Browser compatibility
---------------------

Desktop

Mobile

Chrome

Edge

Firefox

Internet Explorer

Opera

Safari

WebView Android

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

`clear`

38

12

19

11

25

8

38

38

19

25

8

3.0

See also
--------

-   [`Map`](../map)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/clear" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/clear</a>
