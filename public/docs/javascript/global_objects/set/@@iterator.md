Set.prototype\[@@iterator\]()
=============================

The initial value of the `@@iterator` property is the same function object as the initial value of the [`values`](values) property.

Syntax
------

    mySet[Symbol.iterator]

### Return value

The `Set` **iterator** function, which is the [`values()`](values) function by default.

Examples
--------

### Using \[@@iterator\]()

    const mySet = new Set();
    mySet.add('0');
    mySet.add(1);
    mySet.add({});

    const setIter = mySet[Symbol.iterator]();

    console.log(setIter.next().value); // "0"
    console.log(setIter.next().value); // 1
    console.log(setIter.next().value); // Object

### Using \[@@iterator\]() with for..of

    const mySet = new Set();
    mySet.add('0');
    mySet.add(1);
    mySet.add({});

    for (const v of mySet) {
      console.log(v);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-set.prototype-@@iterator">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-set.prototype-@@iterator</span></a></td></tr></tbody></table>

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

`@@iterator`

43

12

36

27-36

A placeholder property named `@@iterator` is used.

17-27

A placeholder property named `iterator` is used.

No

30

9

43

43

36

27-36

A placeholder property named `@@iterator` is used.

17-27

A placeholder property named `iterator` is used.

30

9

4.0

See also
--------

-   [`Set.prototype.entries()`](entries)
-   [`Set.prototype.keys()`](values)
-   [`Set.prototype.values()`](values)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/@@iterator" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/@@iterator</a>
