String.prototype\[@@iterator\]()
================================

The `[@@iterator]()` method returns a new iterator object that iterates over the code points of a String value, returning each code point as a String value.

Syntax
------

    str[Symbol.iterator]

### Return value

A new iterator object.

Examples
--------

### Using \[@@iterator\]()

    var str = 'A\uD835\uDC68';

    var strIter = str[Symbol.iterator]();

    console.log(strIter.next().value); // "A"
    console.log(strIter.next().value); // "\uD835\uDC68"

### Using \[@@iterator\]() with for..of

    var str = 'A\uD835\uDC68B\uD835\uDC69C\uD835\uDC6A';

    for (var v of str) {
      console.log(v);
    }
    // "A"
    // "\uD835\uDC68"
    // "B"
    // "\uD835\uDC69"
    // "C"
    // "\uD835\uDC6A"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-string.prototype-@@iterator">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-string.prototype-@@iterator</span></a></td></tr></tbody></table>

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

38

12

36

27-36

A placeholder property named `@@iterator` is used.

17-27

A placeholder property named `iterator` is used.

No

25

9

38

38

36

27-36

A placeholder property named `@@iterator` is used.

17-27

A placeholder property named `iterator` is used.

25

9

3.0

See also
--------

-   [Iteration protocols](../../iteration_protocols)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/@@iterator" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/@@iterator</a>
