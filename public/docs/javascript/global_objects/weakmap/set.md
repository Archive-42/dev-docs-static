WeakMap.prototype.set()
=======================

The `set()` method adds a new element with a specified key and value to a `WeakMap` object.

Syntax
------

    set(key, value)

### Parameters

`key`  
Required. Must be `object`. The key of the element to add to the `WeakMap` object.

`value`  
Required. Any value. The value of the element to add to the `WeakMap` object.

### Return value

The `WeakMap` object.

Examples
--------

### Using the set() method

    var wm = new WeakMap();
    var obj = {};

    // Add new elements to the WeakMap
    wm.set(obj, 'foo').set(window, 'bar'); // chainable

    // Update an element in the WeakMap
    wm.set(obj, 'baz');

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-weakmap.prototype.set">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-weakmap.prototype.set</span></a></td></tr></tbody></table>

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

36

12

6

Prior to Firefox 38, this method threw a `TypeError` when the key parameter was not an object. This has been fixed in version 38 and later to return `false` as per the ES2015 standard.

11

Returns 'undefined' instead of the 'Map' object.

23

8

37

36

6

Prior to Firefox 38, this method threw a `TypeError` when the key parameter was not an object. This has been fixed in version 38 and later to return `false` as per the ES2015 standard.

24

8

3.0

See also
--------

-   [`WeakMap`](../weakmap)
-   [`WeakMap.prototype.get()`](get)
-   [`WeakMap.prototype.has()`](has)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakMap/set" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakMap/set</a>
