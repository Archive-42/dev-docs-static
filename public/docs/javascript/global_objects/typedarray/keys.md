TypedArray.prototype.keys()
===========================

The `keys()` method returns a new array iterator object that contains the keys for each index in the array.

Syntax
------

    keys()

### Return value

A new array iterator object.

Examples
--------

### Iteration using for...of loop

    var arr = new Uint8Array([10, 20, 30, 40, 50]);
    var eArray = arr.keys();
    // your browser must support for..of loop
    // and let-scoped variables in for loops
    for (let n of eArray) {
      console.log(n);
    }

### Alternative iteration

    var arr = new Uint8Array([10, 20, 30, 40, 50]);
    var eArr = arr.keys();
    console.log(eArr.next().value); // 0
    console.log(eArr.next().value); // 1
    console.log(eArr.next().value); // 2
    console.log(eArr.next().value); // 3
    console.log(eArr.next().value); // 4

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="#">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-%typedarray%.prototype.keys</span></a></td></tr></tbody></table>

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

`keys`

38

14

37

No

25

10

38

38

37

25

10

3.0

See also
--------

-   [JavaScript typed arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Typed_arrays)
-   [`TypedArray`](../typedarray)
-   [`TypedArray.prototype.entries()`](entries)
-   [`TypedArray.prototype.values()`](values)
-   [`TypedArray.prototype[@@iterator]()`](@@iterator)
-   [for...of](../../statements/for...of)
-   [Iteration protocols](../../iteration_protocols)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/keys" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/keys</a>
