WeakMap.prototype.has()
=======================

The `has()` method returns a boolean indicating whether an element with the specified key exists in the `WeakMap` object or not.

Syntax
------

    has(key)

### Parameters

`key`  
Required. The key of the element to test for presence in the `WeakMap` object.

### Return value

Boolean  
Returns `true` if an element with the specified key exists in the `WeakMap` object; otherwise `false`.

Examples
--------

### Using the has method

    var wm = new WeakMap();
    wm.set(window, 'foo');

    wm.has(window); // returns true
    wm.has('baz');  // returns false

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-weakmap.prototype.has">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-weakmap.prototype.has</span></a></td></tr></tbody></table>

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

36

12

6

Prior to Firefox 38, this method threw a `TypeError` when the key parameter was not an object. This has been fixed in version 38 and later to return `false` as per the ES2015 standard.

11

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
-   [`WeakMap.prototype.set()`](set)
-   [`WeakMap.prototype.get()`](get)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakMap/has" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakMap/has</a>
