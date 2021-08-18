Map.prototype.entries()
=======================

The `entries()` method returns a new **[Iterator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Iterators_and_Generators)** object that contains the `[key, value]` pairs for each element in the `Map` object in insertion order. In this particular case, this iterator object is also an iterable, so the for-of loop can be used. When the protocol `[Symbol.iterator]` is used, it returns a function that, when invoked, returns this iterator itself.

Syntax
------

    entries()

### Return value

A new [`Map`](../map) iterator object.

Examples
--------

### Using entries()

    let myMap = new Map()
    myMap.set('0', 'foo')
    myMap.set(1, 'bar')
    myMap.set({}, 'baz')

    let mapIter = myMap.entries()

    console.log(mapIter.next().value)  // ["0", "foo"]
    console.log(mapIter.next().value)  // [1, "bar"]
    console.log(mapIter.next().value)  // [Object, "baz"]

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-map.prototype.entries">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-map.prototype.entries</span></a></td></tr></tbody></table>

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

`entries`

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

-   [`Map.prototype.keys()`](keys)
-   [`Map.prototype.values()`](values)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/entries" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/entries</a>
