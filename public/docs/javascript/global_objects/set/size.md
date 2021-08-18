Set.prototype.size
==================

The `size` accessor property returns the number of (unique) elements in a [`Set`](../set) object.

Description
-----------

The value of `size` is an integer representing how many entries the `Set` object has. A set accessor function for `size` is `undefined`; you cannot change this property.

Examples
--------

### Using size

    var mySet = new Set();
    mySet.add(1);
    mySet.add(5);
    mySet.add('some text')

    mySet.size; // 3

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-get-set.prototype.size">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-get-set.prototype.size</span></a></td></tr></tbody></table>

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

`size`

38

12

19

From Firefox 13 to Firefox 18, the `size` property was implemented as a `Set.prototype.size()` method, this has been changed to a property in later versions conform to the ECMAScript 2015 specification.

11

25

8

38

38

19

From Firefox 13 to Firefox 18, the `size` property was implemented as a `Set.prototype.size()` method, this has been changed to a property in later versions conform to the ECMAScript 2015 specification.

25

8

3.0

See also
--------

-   [`Set`](../set)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/size" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/size</a>
