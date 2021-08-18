TypedArray.prototype.find()
===========================

The `find()` method returns a value of an element in the typed array, if it satisfies the provided testing function. Otherwise [`undefined`](../undefined) is returned. *TypedArray* is one of the [typed array types](../typedarray#typedarray_objects) here.

See also the [`findIndex()`](findindex) method, which returns the **index** of a found element in the typed array instead of its value.

Syntax
------

    // Arrow function
    find((element) => { ... } )
    find((element, index) => { ... } )
    find((element, index, array) => { ... } )

    // Callback function
    find(callbackFn)
    find(callbackFn, thisArg)

    // Inline callback function
    find(function callbackFn(element) { ... })
    find(function callbackFn(element, index) { ... })
    find(function callbackFn(element, index, array){ ... })
    find(function callbackFn(element, index, array) { ... }, thisArg)

### Parameters

`callbackFn`  
Function to execute on each value in the typed array, taking three arguments:

`element`  
The current element being processed in the typed array.

`index`  
The index of the current element being processed in the typed array.

`array`  
The array `find()` was called upon.

 `thisArg` <span class="badge inline optional">Optional</span>   
Object to use as `this` when executing `callbackFn`.

### Return value

A value in the array if an element passes the test; otherwise, [`undefined`](../undefined).

Description
-----------

The `find()` method executes the `callbackFn` function once for each element present in the typed array until it finds one where `callbackFn` returns a true value. If such an element is found, `find()` immediately returns the value of that element. Otherwise, `find()` returns [`undefined`](../undefined). `callbackFn` is invoked only for indexes of the typed array which have assigned values; it is not invoked for indexes which have been deleted or which have never been assigned values.

`callbackFn` is invoked with three arguments: the value of the element, the index of the element, and the typed array object being traversed.

If a `thisArg` parameter is provided to `find()`, it will be used as the `this` for each invocation of the `callbackFn`. If it is not provided, then [`undefined`](../undefined) is used.

`find()` does not mutate the typed array on which it is called.

The range of elements processed by `find()` is set before the first invocation of `callbackFn`. Elements that are appended to the typed array after the call to `find()` begins will not be visited by `callbackFn`. If an existing, unvisited element of the typed array is changed by `callbackFn`, its value passed to the visiting `callbackFn` will be the value at the time that `find()` visits that element's index; elements that are deleted are not visited.

Examples
--------

### Find a prime number in a typed array

The following example finds an element in the typed array that is a prime number (or returns [`undefined`](../undefined) if there is no prime number).

    function isPrime(element, index, array) {
      var start = 2;
      while (start <= Math.sqrt(element)) {
        if (element % start++ < 1) {
          return false;
        }
      }
      return element > 1;
    }

    var uint8 = new Uint8Array([4, 5, 8, 12]);
    console.log(uint8.find(isPrime)); // 5

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="#">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-%typedarray%.prototype.find</span></a></td></tr></tbody></table>

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

`find`

45

14

37

No

32

9.1

45

45

37

32

9.3

5.0

See also
--------

-   [`TypedArray.prototype.findIndex()`](findindex)
-   [`TypedArray.prototype.every()`](every)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/find" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/find</a>
