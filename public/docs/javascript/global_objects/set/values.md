Set.prototype.values()
======================

The `values()` method returns a new iterator object that contains the values for each element in the `Set` object in insertion order.

**Note:** The `keys()` method is an alias for this method (for similarity with [`Map`](../map) objects), hence the `keys()` page redirecting here. It behaves exactly the same and returns **values** of `Set` elements.

Syntax
------

    values()

### Return value

A new iterator object containing the values for each element in the given `Set`, in insertion order.

Examples
--------

### Using values()

    var mySet = new Set();
    mySet.add('foo');
    mySet.add('bar');
    mySet.add('baz');

    var setIter = mySet.values();

    console.log(setIter.next().value); // "foo"
    console.log(setIter.next().value); // "bar"
    console.log(setIter.next().value); // "baz"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-set.prototype.values">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-set.prototype.values</span></a></td></tr></tbody></table>

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

`values`

38

38

12

12

24

24

No

25

25

8

8

38

38

38

38

24

24

25

25

8

8

3.0

3.0

See also
--------

-   [`Set.prototype.entries()`](entries)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/values" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/values</a>
