Map.prototype.has()
===================

The `has()` method returns a boolean indicating whether an element with the specified key exists or not.

Syntax
------

    has(key)

### Parameters

`key`  
The key of the element to test for presence in the `Map` object.

### Return value

`true` if an element with the specified key exists in the `Map` object; otherwise `false`.

Examples
--------

### Using has()

    let myMap = new Map()
    myMap.set('bar', "foo")

    myMap.has('bar')   // returns true
    myMap.has('baz')   // returns false

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-map.prototype.has">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-map.prototype.has</span></a></td></tr></tbody></table>

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

`has`

38

12

13

11

25

8

38

38

14

25

8

3.0

See also
--------

-   [`Map`](../map)
-   [`Map.prototype.set()`](set)
-   [`Map.prototype.get()`](get)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/has" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/has</a>
