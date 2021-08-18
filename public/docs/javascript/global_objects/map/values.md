Map.prototype.values()
======================

The `values()` method returns a new **[Iterator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Iterators_and_Generators)** object that contains the values for each element in the `Map` object in insertion order.

Syntax
------

    values()

### Return value

A new [`Map`](../map) iterator object.

Examples
--------

### Using values()

    var myMap = new Map();
    myMap.set('0', 'foo');
    myMap.set(1, 'bar');
    myMap.set({}, 'baz');

    var mapIter = myMap.values();

    console.log(mapIter.next().value); // "foo"
    console.log(mapIter.next().value); // "bar"
    console.log(mapIter.next().value); // "baz"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-map.prototype.values">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-map.prototype.values</span></a></td></tr></tbody></table>

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

`values`

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
-   [`Map.prototype.keys()`](keys)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/values" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/values</a>
