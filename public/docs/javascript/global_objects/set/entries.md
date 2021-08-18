Set.prototype.entries()
=======================

The `entries()` method returns a new [Iterator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Iterators_and_Generators) object that contains `[value, value]` for each element in the `Set` object, in insertion order. For `Set` objects there is no `key` like in `Map` objects. However, to keep the API similar to the `Map` object, each *entry* has the same value for its *key* and *value* here, so that an array `[value, value]` is returned.

Syntax
------

    entries()

### Return value

A new iterator object that contains an array of `[value, value]` for each element in the given `Set`, in insertion order.

Examples
--------

### Using entries()

    var mySet = new Set();
    mySet.add('foobar');
    mySet.add(1);
    mySet.add('baz');

    var setIter = mySet.entries();

    console.log(setIter.next().value); // ["foobar", "foobar"]
    console.log(setIter.next().value); // [1, 1]
    console.log(setIter.next().value); // ["baz", "baz"]

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-set.prototype.entries">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-set.prototype.entries</span></a></td></tr></tbody></table>

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

`entries`

38

12

24

No

25

8

38

38

24

25

8

3.0

See also
--------

-   [`Set.prototype.keys()`](values)
-   [`Set.prototype.values()`](values)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/entries" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/entries</a>
