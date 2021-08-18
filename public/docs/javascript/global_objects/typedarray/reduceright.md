TypedArray.prototype.reduceRight()
==================================

The `reduceRight()` method applies a function against an accumulator and each value of the typed array (from right-to-left) has to reduce it to a single value. This method has the same algorithm as [`Array.prototype.reduceRight()`](../array/reduceright). *TypedArray* is one of the [typed array types](../typedarray#typedarray_objects) here.

Syntax
------

    // Arrow function
    reduceRight((accumulator, currentValue) => { ... } )
    reduceRight((accumulator, currentValue, index) => { ... } )
    reduceRight((accumulator, currentValue, index, array) => { ... } )
    reduceRight((accumulator, currentValue, index, array) => { ... }, initialValue)

    // Callback function
    reduceRight(callbackFn)
    reduceRight(callbackFn, initialValue)

    // Inline callback function
    reduceRight(function callbackFn(accumulator, currentValue) { ... })
    reduceRight(function callbackFn(accumulator, currentValue, index) { ... })
    reduceRight(function callbackFn(accumulator, currentValue, index, array){ ... })
    reduceRight(function callbackFn(accumulator, currentValue, index, array) { ... }, thisArg)

### Parameters

`callbackFn`  
Function to execute on each value in the typed array, taking four arguments:

`accumulator`  
The value previously returned in the last invocation of the callback, or `initialValue`, if supplied (see below).

`currentValue`  
The current element being processed in the typed array.

`index`  
The index of the current element being processed in the typed array.

`array`  
The typed array `reduceRight()` was called upon.

`initialValue`  
Optional. Object to use as the first argument to the first call of the `callbackFn`.

### Return value

The value that results from the reduction.

Description
-----------

The `reduceRight` method executes the `callbackFn` function once for each element present in the typed array, excluding holes in the typed array, receiving four arguments: the initial value (or value from the previous `callbackFn` call), the value of the current element, the current index, and the typed array over which iteration is occurring.

The call to the `reduceRight` callback would look something like this:

    typedarray.reduceRight(function(accumulator, currentValue, index, typedarray) {
      // ...
    });

The first time the function is called, the `accumulator` and `currentValue` can be one of two values. If an `initialValue` was provided in the call to `reduceRight`, then `accumulator` will be equal to `initialValue` and `currentValue` will be equal to the last value in the typed array. If no `initialValue` was provided, then `accumulator` will be equal to the last value in the typed array and `currentValue` will be equal to the second-to-last value.

If the typed array is empty and no `initialValue` was provided, [`TypeError`](../typeerror) would be thrown. If the typed array has only one element (regardless of position) and no `initialValue` was provided, or if `initialValue` is provided but the typed array is empty, the solo value would be returned without calling `callbackFn`.

Examples
--------

### Sum up all values within an array

    var total = new Uint8Array([0, 1, 2, 3]).reduceRight(function(a, b) {
      return a + b;
    });
    // total == 6

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="#">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-%typedarray%.prototype.reduceright</span></a></td></tr></tbody></table>

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

`reduceRight`

45

14

37

No

32

10

45

45

37

No

10

5.0

See also
--------

-   [`TypedArray.prototype.reduce()`](reduce)
-   [`Array.prototype.reduceRight()`](../array/reduceright)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/reduceRight" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/reduceRight</a>
