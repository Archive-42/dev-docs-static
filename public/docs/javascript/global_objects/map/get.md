Map.prototype.get()
===================

The `get()` method returns a specified element from a `Map` object. If the value that is associated to the provided key is an object, then you will get a reference to that object and any change made to that object will effectively modify it inside the `Map` object.

Syntax
------

    get(key)

### Parameters

`key`  
The key of the element to return from the `Map` object.

### Return value

The element associated with the specified key, or [`undefined`](../undefined) if the key can't be found in the `Map` object.

Examples
--------

### Using get()

    let myMap = new Map();
    myMap.set('bar', 'foo');

    myMap.get('bar');   // Returns "foo"
    myMap.get('baz');   // Returns undefined

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-map.prototype.get">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-map.prototype.get</span></a></td></tr></tbody></table>

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

`get`

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
-   [`Map.prototype.has()`](has)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/get" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/get</a>
