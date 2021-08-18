WeakSet.prototype.has()
=======================

The `has()` method returns a boolean indicating whether an object exists in a `WeakSet` or not.

Syntax
------

    has(value)

### Parameters

`value`  
Required. The object to test for presence in the `WeakSet`.

### Return value

Boolean  
Returns `true` if an element with the specified value exists in the `WeakSet` object; otherwise `false`.

Examples
--------

### Using the has method

    var ws = new WeakSet();
    var obj = {};
    ws.add(window);

    mySet.has(window);  // returns true
    mySet.has(obj);     // returns false

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-weakset.prototype.has">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-weakset.prototype.has</span></a></td></tr></tbody></table>

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
-   [`WeakSet.prototype.add()`](add)
-   [`WeakSet.prototype.delete()`](delete)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakSet/has" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakSet/has</a>
