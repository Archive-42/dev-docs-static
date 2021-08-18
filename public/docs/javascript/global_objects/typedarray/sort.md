TypedArray.prototype.sort()
===========================

The `sort()` method sorts the elements of a typed array numerically *in place* and returns the typed array. This method has the same algorithm as [`Array.prototype.sort()`](../array/sort), except that sorts the values numerically instead of as strings. *TypedArray* is one of the [typed array types](../typedarray#typedarray_objects) here.

Syntax
------

    // Functionless
    sort()

    // Arrow function
    sort((firstEl, secondEl) => { ... } )

    // Compare function
    sort(compareFn)

    // Inline compare function
    sort(function compareFn(firstEl, secondEl) { ... })

### Parameters

 `compareFunction` <span class="badge inline optional">Optional</span>   
Specifies a function that defines the sort order.

### Return value

The sorted typed array.

Examples
--------

### Using sort

For more examples, see also the [`Array.prototype.sort()`](../array/sort) method.

    let numbers = new Uint8Array([40, 1, 5, 200]);
    numbers.sort();
    // Uint8Array [ 1, 5, 40, 200 ]
    // Unlike plain Arrays, a compare function is not required
    // to sort the numbers numerically.

    // Regular Arrays require a compare function to sort numerically:
    numbers = [40, 1, 5, 200];
    numbers.sort();
    // [1, 200, 40, 5]

    numbers.sort((a, b) => a - b); // compare numbers
    // [ 1, 5, 40, 200 ]

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="#">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-%typedarray%.prototype.sort</span></a></td></tr></tbody></table>

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

`sort`

45

14

46

No

32

10

45

45

46

32

10

5.0

See also
--------

-   [`Array.prototype.sort()`](../array/sort)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/sort" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/sort</a>
