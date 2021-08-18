TypedArray.prototype.entries()
==============================

The `entries()` method returns a new [`Array`](../array) iterator object that contains the key/value pairs for each index in the array.

Syntax
------

    entries()

### Return value

A new array iterator object.

Examples
--------

### Iteration using for...of loop

    var arr = new Uint8Array([10, 20, 30, 40, 50]);
    var eArray = arr.entries();
    // your browser must support for..of loop
    // and let-scoped variables in for loops
    for (let n of eArray) {
      console.log(n);
    }

### Alternative iteration

    var arr = new Uint8Array([10, 20, 30, 40, 50]);
    var eArr = arr.entries();
    console.log(eArr.next().value); // [0, 10]
    console.log(eArr.next().value); // [1, 20]
    console.log(eArr.next().value); // [2, 30]
    console.log(eArr.next().value); // [3, 40]
    console.log(eArr.next().value); // [4, 50]

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="#">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-%typedarray%.prototype.entries</span></a></td></tr></tbody></table>

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

45

14

37

No

36

9.1

No

45

37

No

9.3

5.0

See also
--------

-   [JavaScript typed arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Typed_arrays)
-   [`TypedArray`](../typedarray)
-   [`TypedArray.prototype.keys()`](keys)
-   [`TypedArray.prototype.values()`](values)
-   [`TypedArray.prototype[@@iterator]()`](@@iterator)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/entries" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/entries</a>
