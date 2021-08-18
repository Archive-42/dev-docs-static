Map.prototype.keys()
====================

The `keys()` method returns a new **[Iterator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Iterators_and_Generators)** object that contains the keys for each element in the `Map` object in insertion order.

Syntax
------

    keys()

### Return value

A new [`Map`](../map) iterator object.

Examples
--------

### Using keys()

    var myMap = new Map();
    myMap.set('0', 'foo');
    myMap.set(1, 'bar');
    myMap.set({}, 'baz');

    var mapIter = myMap.keys();

    console.log(mapIter.next().value); // "0"
    console.log(mapIter.next().value); // 1
    console.log(mapIter.next().value); // Object

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-map.prototype.keys">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-map.prototype.keys</span></a></td></tr></tbody></table>

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

`keys`

38

12

20

No

25

8

38

38

20

25

8

3.0

See also
--------

-   [`Map.prototype.entries()`](entries)
-   [`Map.prototype.values()`](values)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/keys" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/keys</a>
