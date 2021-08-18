TypedArray.prototype.filter()
=============================

The `filter()` method creates a new typed array with all elements that pass the test implemented by the provided function. This method has the same algorithm as [`Array.prototype.filter()`](../array/filter). *TypedArray* is one of the [typed array types](../typedarray#typedarray_objects) here.

Syntax
------

    // Arrow function
    filter((element) => { ... } )
    filter((element, index) => { ... } )
    filter((element, index, array) => { ... } )

    // Callback function
    filter(callbackFn)
    filter(callbackFn, thisArg)

    // Inline callback function
    filter(function callbackFn(element) { ... })
    filter(function callbackFn(element, index) { ... })
    filter(function callbackFn(element, index, array){ ... })
    filter(function callbackFn(element, index, array) { ... }, thisArg)

### Parameters

`callbackFn`  
Function to test each element of the typed array. Invoked with arguments `(element, index, array)`. Return `true` to keep the element, `false` otherwise.

 `thisArg`<span class="badge inline optional">Optional</span>   
Value to use as `this` when executing `callbackFn`.

### Return value

A new typed array with the elements that pass the test.

Description
-----------

The `filter()` method calls a provided `callbackFn` function once for each element in a typed array, and constructs a new typed array of all the values for which `callbackFn` returns [a value that coerces to `true`](https://developer.mozilla.org/en-US/docs/Glossary/Truthy). `callbackFn` is invoked only for indexes of the typed array which have assigned values; it is not invoked for indexes which have been deleted or which have never been assigned values. Typed array elements which do not pass the `callbackFn` test are skipped, and are not included in the new typed array.

`callbackFn` is invoked with three arguments:

1.  the value of the element
2.  the index of the element
3.  the typed array object being traversed

If a `thisArg` parameter is provided to `filter()`, it will be passed to `callbackFn` when invoked, for use as its `this` value. Otherwise, the value `undefined` will be passed for use as its `this` value. The `this` value ultimately observable by `callbackFn` is determined according to [the usual rules for determining the `this` seen by a function](../../operators/this).

`filter()` does not mutate the typed array on which it is called.

The range of elements processed by `filter()` is set before the first invocation of `callbackFn`. Elements which are appended to the typed array after the call to `filter()` begins will not be visited by `callbackFn`. If existing elements of the typed array are changed, or deleted, their value as passed to `callbackFn` will be the value at the time `filter()` visits them; elements that are deleted are not visited.

Examples
--------

### Filtering out all small values

The following example uses `filter()` to create a filtered typed array that has all elements with values less than 10 removed.

    function isBigEnough(element, index, array) {
      return element >= 10;
    }
    new Uint8Array([12, 5, 8, 130, 44]).filter(isBigEnough);
    // Uint8Array [ 12, 130, 44 ]

### Filtering typed array elements using arrow functions

[Arrow functions](../../functions/arrow_functions) provide a shorter syntax for the same test.

    new Uint8Array([12, 5, 8, 130, 44]).filter(elem => elem >= 10);
    // Uint8Array [ 12, 130, 44 ]

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="#">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-%typedarray%.prototype.filter</span></a></td></tr></tbody></table>

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

`filter`

45

14

38

No

No

9.1

No

45

38

No

9.3

5.0

See also
--------

-   [`TypedArray.prototype.every()`](every)
-   [`TypedArray.prototype.some()`](some)
-   [`Array.prototype.filter()`](../array/filter)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/filter" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/filter</a>
