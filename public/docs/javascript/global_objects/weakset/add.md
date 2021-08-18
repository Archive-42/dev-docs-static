WeakSet.prototype.add()
=======================

The `add()` method appends a new object to the end of a `WeakSet` object.

Syntax
------

    add(value)

### Parameters

value  
Required. The object to add to the `WeakSet` collection.

### Return value

The `WeakSet` object.

Examples
--------

### Using add

    var ws = new WeakSet();

    ws.add(window); // add the window object to the WeakSet

    ws.has(window); // true

    // Weakset only takes objects as arguments
    ws.add(1);
    // results in "TypeError: Invalid value used in weak set" in Chrome
    // and "TypeError: 1 is not a non-null object" in Firefox

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-weakset.prototype.add">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-weakset.prototype.add</span></a></td></tr></tbody></table>

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

`add`

36

12

34

No

23

9

37

36

34

24

9

3.0

See also
--------

-   [`WeakSet`](../weakset)
-   [`WeakSet.prototype.delete()`](delete)
-   [`WeakSet.prototype.has()`](has)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakSet/add" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakSet/add</a>
