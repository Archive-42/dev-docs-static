TypedArray.prototype\[@@iterator\]()
====================================

The initial value of the `@@iterator` property is the same function object as the initial value of the [`values`](values) property.

Syntax
------

    [Symbol.iterator]()

### Return value

The array **iterator** function, which is the [`values()`](values) function by default.

Examples
--------

### Iteration using for...of loop

    var arr = new Uint8Array([10, 20, 30, 40, 50]);
    // your browser must support for..of loop
    // and let-scoped variables in for loops
    for (let n of arr) {
      console.log(n);
    }

### Alternative iteration

    var arr = new Uint8Array([10, 20, 30, 40, 50]);
    var eArr = arr[Symbol.iterator]();
    console.log(eArr.next().value); // 10
    console.log(eArr.next().value); // 20
    console.log(eArr.next().value); // 30
    console.log(eArr.next().value); // 40
    console.log(eArr.next().value); // 50

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="#">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-%typedarray%.prototype-@@iterator</span></a></td></tr></tbody></table>

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

10

38

38

36

27-36

A placeholder property named `@@iterator` is used.

17-27

A placeholder property named `iterator` is used.

25

10

3.0

See also
--------

-   [JavaScript typed arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Typed_arrays)
-   [`TypedArray`](../typedarray)
-   [`TypedArray.prototype.entries()`](entries)
-   [`TypedArray.prototype.keys()`](keys)
-   [`TypedArray.prototype.values()`](values)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/@@iterator" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/@@iterator</a>
