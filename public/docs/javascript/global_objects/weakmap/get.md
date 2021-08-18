WeakMap.prototype.get()
=======================

The `get()` method returns a specified element from a `WeakMap` object.

Syntax
------

    get(key)

### Parameters

`key`  
Required. The key of the element to return from the `WeakMap` object.

### Return value

The element associated with the specified key in the `WeakMap` object. If the key can't be found, [`undefined`](../undefined) is returned.

Examples
--------

### Using the get() method

    var wm = new WeakMap();
    wm.set(window, 'foo');

    wm.get(window); // Returns "foo".
    wm.get('baz');  // Returns undefined.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-weakmap.prototype.get">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-weakmap.prototype.get</span></a></td></tr></tbody></table>

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

36

12

6

Prior to Firefox 38, this method threw a `TypeError` when the key parameter was not an object. However, the ES2015 specification specifies to return `undefined` instead. Furthermore, `WeakMap.prototype.get` accepted an optional second argument as a fallback value, which is not part of the standard. Both non-standard behaviors are removed in version 38 and higher.

11

23

8

37

36

6

Prior to Firefox 38, this method threw a `TypeError` when the key parameter was not an object. However, the ES2015 specification specifies to return `undefined` instead. Furthermore, `WeakMap.prototype.get` accepted an optional second argument as a fallback value, which is not part of the standard. Both non-standard behaviors are removed in version 38 and higher.

24

8

3.0

See also
--------

-   [`WeakMap`](../weakmap)
-   [`WeakMap.set()`](set)
-   [`WeakMap.has()`](has)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakMap/get" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakMap/get</a>
