TypedArray.prototype.forEach()
==============================

The `forEach()` method executes a provided function once per array element. This method has the same algorithm as [`Array.prototype.forEach()`](../array/foreach). *TypedArray* is one of the [typed array types](../typedarray#typedarray_objects) here.

Syntax
------

    // Arrow function
    forEach((element) => { ... } )
    forEach((element, index) => { ... } )
    forEach((element, index, array) => { ... } )

    // Callback function
    forEach(callbackFn)
    forEach(callbackFn, thisArg)

    // Inline callback function
    forEach(function callbackFn(element) { ... })
    forEach(function callbackFn(element, index) { ... })
    forEach(function callbackFn(element, index, array){ ... })
    forEach(function callbackFn(element, index, array) { ... }, thisArg)

### Parameters

`callbackFn`  
Function that produces an element of the new typed array, taking three arguments:

`element`  
The current element being processed in the typed array.

`index`  
The index of the current element being processed in the array.

`array`  
The array `forEach()` was called upon.

 `thisArg` <span class="badge inline optional">Optional</span>   
Value to use as `this` when executing `callbackFn`.

### Return value

[`undefined`](../undefined).

Description
-----------

The `forEach()` method executes the provided `callbackFn` once for each element present in the typed array in ascending order. It is not invoked for indexes that have been deleted or elided. However, it is executed for elements that are present and have the value [`undefined`](../undefined).

`callbackFn` is invoked with **three arguments**:

-   the **element value**
-   the **element index**
-   the **typed array being traversed**

If a `thisArg` parameter is provided to `forEach()`, it will be passed to `callbackFn` when invoked, for use as its `this` value. Otherwise, the value [`undefined`](../undefined) will be passed for use as its `this` value. The `this` value ultimately observable by `callbackFn` is determined according to [the usual rules for determining the `this` seen by a function](../../operators/this).

The range of elements processed by `forEach()` is set before the first invocation of `callbackFn`. Elements that are appended to the typed array after the call to `forEach()` begins will not be visited by `callbackFn` . If the values of existing elements of the typed array are changed, the value passed to `callbackFn` will be the value at the time `forEach()` visits them; elements that are deleted before being visited are not visited.

`forEach()` executes the `callbackFn` function once for each typed array element; unlike [`every()`](every) and [`some()`](some) it, always returns the value [`undefined`](../undefined).

Examples
--------

### Logging the contents of a typed array

The following code logs a line for each element in a typed array:

    function logArrayElements(element, index, array) {
      console.log('a[' + index + '] = ' + element);
    }

    new Uint8Array([0, 1, 2, 3]).forEach(logArrayElements);
    // logs:
    // a[0] = 0
    // a[1] = 1
    // a[2] = 2
    // a[3] = 3

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="#">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-%typedarray%.prototype.foreach</span></a></td></tr></tbody></table>

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

`forEach`

45

14

38

No

32

10

45

45

38

32

10

5.0

See also
--------

-   [`TypedArray.prototype.map()`](map)
-   [`TypedArray.prototype.every()`](every)
-   [`TypedArray.prototype.some()`](some)
-   [`Array.prototype.forEach()`](../array/foreach)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/forEach" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/forEach</a>
