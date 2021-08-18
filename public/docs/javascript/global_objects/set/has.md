Set.prototype.has()
===================

The `has()` method returns a boolean indicating whether an element with the specified value exists in a `Set` object or not.

Syntax
------

    has(value)

### Parameters

`value`  
The value to test for presence in the `Set` object.

### Return value

Returns `true` if an element with the specified value exists in the `Set` object; otherwise `false`.

**Note:** Technically speaking, `has()` uses the [Same-value-zero](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Equality_comparisons_and_sameness#same-value-zero_equality) algorithm to determine whether the given element is found.

Examples
--------

### Using the has() method

    var mySet = new Set();
    mySet.add('foo');

    mySet.has('foo');  // returns true
    mySet.has('bar');  // returns false

    var set1 = new Set();
    var obj1 = {'key1': 1};
    set1.add(obj1);

    set1.has(obj1);        // returns true
    set1.has({'key1': 1}); // returns false because they are different object references
    set1.add({'key1': 1}); // now set1 contains 2 entries

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-set.prototype.has">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-set.prototype.has</span></a></td></tr></tbody></table>

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

-   [`Set`](../set)
-   [`Set.prototype.add()`](add)
-   [`Set.prototype.delete()`](delete)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/has" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/has</a>
