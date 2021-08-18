TypedArray.prototype.map()
==========================

The `map()` method creates a new typed array with the results of calling a provided function on every element in this typed array. This method has the same algorithm as [`Array.prototype.map()`](../array/map)*.* *TypedArray* is one of the [typed array types](../typedarray#typedarray_objects) here.

Syntax
------

    // Arrow function
    map((currentValue) => { ... } )
    map((currentValue, index) => { ... } )
    map((currentValue, index, array) => { ... } )

    // Callback function
    map(callbackFn)
    map(callbackFn, thisArg)

    // Inline callback function
    map(function callbackFn(currentValue) { ... })
    map(function callbackFn(currentValue, index) { ... })
    map(function callbackFn(currentValue, index, array){ ... })
    map(function callbackFn(currentValue, index, array) { ... }, thisArg)

### Parameters

`callbackFn`  
A callback function that produces an element of the new typed array, taking three arguments:

`currentValue`  
The current element being processed in the typed array.

 `index` <span class="badge inline optional">Optional</span>   
The index of the current element being processed in the typed array.

 `array` <span class="badge inline optional">Optional</span>   
The typed array `map()` was called upon.

 `thisArg` <span class="badge inline optional">Optional</span>   
Value to use as `this` when executing `callbackFn`.

### Return value

A new typed array.

Description
-----------

The `map()` method calls a provided callback function (`callbackFn`) once for each element in a typed array, in order, and constructs a new typed array from the results.

`callbackFn` is invoked only for indexes of the typed array which have assigned values; it is not invoked for indexes that are `undefined`, those which have been deleted, or which have never been assigned values.

`callbackFn` is invoked with three arguments: the value of the element, the index of the element, and the typed array object being traversed.

If a `thisArg` parameter is provided to `map()`, it will be passed to `callbackFn` when invoked, for use as its `this` value. Otherwise, the value [`undefined`](../undefined) will be passed for use as its `this` value. The `this` value ultimately observable by `callbackFn` is determined according to [the usual rules for determining the `this` seen by a function](../../operators/this).

`map()` does not mutate the typed array on which it is called (although `callbackFn`, if invoked, may do so).

The range of elements processed by `map()` is set before the first invocation of `callbackFn`. Elements which are appended to the array after the call to `map()` begins will not be visited by `callbackFn`. If existing elements of the typed array are changed, or deleted, their value as passed to `callbackFn` will be the value at the time `map()` visits them; elements that are deleted are not visited.

Examples
--------

### Mapping a typed array to a typed array of square roots

The following code takes a typed array and creates a new typed array containing the square roots of the numbers in the first typed array.

    const numbers = new Uint8Array([1, 4, 9]);
    const roots = numbers.map(Math.sqrt);
    // roots is now: Uint8Array [1, 2, 3],
    // numbers is still Uint8Array [1, 4, 9]

### Mapping a typed array of numbers using a function containing an argument

The following code shows how `map()` works when a function requiring one argument is used with it. The argument will automatically be assigned to each element of the typed array as `map()` loops through the original typed array.

    const numbers = new Uint8Array([1, 4, 9]);
    const doubles = numbers.map(function(num) {
      return num * 2;
    });
    // doubles is now Uint8Array [2, 8, 18]
    // numbers is still Uint8Array [1, 4, 9]

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="#">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-%typedarray%.prototype.map</span></a></td></tr></tbody></table>

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

`map`

45

14

38

No

32

9.1

45

45

38

32

9.3

5.0

See also
--------

-   [`TypedArray.prototype.filter()`](filter)
-   [`Array.prototype.map()`](../array/map)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/map" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/map</a>
