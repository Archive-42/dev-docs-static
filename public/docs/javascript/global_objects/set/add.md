Set.prototype.add()
===================

The `add()` method appends a new element with a specified value to the end of a `Set` object.

Syntax
------

    add(value)

### Parameters

`value`  
The value of the element to add to the `Set` object.

### Return value

The `Set` object with added value.

Examples
--------

### Using the add() method

    var mySet = new Set();

    mySet.add(1);
    mySet.add(5).add('some text'); // chainable

    console.log(mySet);
    // Set [1, 5, "some text"]

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-set.prototype.add">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-set.prototype.add</span></a></td></tr></tbody></table>

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

38

12

13

11

Returns 'undefined' instead of the 'Set' object.

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
-   [`Set.prototype.delete()`](delete)
-   [`Set.prototype.has()`](has)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/add" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/add</a>
