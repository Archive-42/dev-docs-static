Map.prototype.set()
===================

The `set()` method adds or updates an element with a specified key and a value to a `Map` object.

Syntax
------

    set(key, value)

### Parameters

`key`  
The key of the element to add to the `Map` object.

`value`  
The value of the element to add to the `Map` object.

### Return value

The `Map` object.

Examples
--------

### Using set()

    let myMap = new Map()

    // Add new elements to the map
    myMap.set('bar', 'foo')
    myMap.set(1, 'foobar')

    // Update an element in the map
    myMap.set('bar', 'baz')

### Using the set() with chaining

Since the `set()` method returns back the same `Map` object, you can chain the method call like below:

    // Add new elements to the map with chaining.
    myMap.set('bar', 'foo')
         .set(1, 'foobar')
         .set(2, 'baz');

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-map.prototype.set">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-map.prototype.set</span></a></td></tr></tbody></table>

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

`set`

38

12

13

11

Returns 'undefined' instead of the 'Map' object.

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
-   [`Map.prototype.get()`](get)
-   [`Map.prototype.has()`](has)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/set" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/set</a>
