TypedArray.prototype.every()
============================

The `every()` method tests whether all elements in the typed array pass the test implemented by the provided function. This method has the same algorithm as [`Array.prototype.every()`](../array/every)*.* *TypedArray* is one of the [typed array types](../typedarray#typedarray_objects) here.

Syntax
------

    // Arrow function
    every((element) => { ... } )
    every((element, index) => { ... } )
    every((element, index, array) => { ... } )

    // Callback function
    every(callbackFn)
    every(callbackFn, thisArg)

    // Inline callback function
    every(function callbackFn(element) { ... })
    every(function callbackFn(element, index) { ... })
    every(function callbackFn(element, index, array){ ... })
    every(function callbackFn(element, index, array) { ... }, thisArg)

### Parameters

`callbackFn`  
A function to test for each element, taking three arguments:

`element`  
The current element being processed in the typed array.

 `index` <span class="badge inline optional">Optional</span>   
The index of the current element being processed in the typed array.

 `array` <span class="badge inline optional">Optional</span>   
The typed array `every` was called upon.

 `thisArg` <span class="badge inline optional">Optional</span>   
A value to use as `this` when executing `callbackFn`.

### Return value

`true` if the callback function returns a [truthy](https://developer.mozilla.org/en-US/docs/Glossary/Truthy) value for every array element; otherwise, `false`.

Description
-----------

The `every` method executes the provided `callbackFn` function once for each element present in the typed array until it finds the one where `callbackFn` returns a [falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy) value. If such an element is found, the `every` method immediately returns `false`. Otherwise, if `callbackFn` returns a [truthy](https://developer.mozilla.org/en-US/docs/Glossary/Truthy) value for all elements, `every` returns `true`.

`callbackFn` is invoked with three arguments: the value of the element, the index of the element, and the typed array object being traversed.

If a `thisArg` parameter is provided to `every`, it will be used as callback's `this` value. Otherwise, the value `undefined` will be used as its `this` value. The `this` value ultimately observable by `callbackFn` is determined according to [the usual rules for determining the `this` seen by a function](../../operators/this).

`every` does not mutate the typed array on which it is called.

Examples
--------

### Testing size of all typed array elements

The following example tests whether all elements in the typed array are bigger than 9.

    function isBigEnough(element, index, array) {
      return element >= 10;
    }
    new Uint8Array([12, 5, 8, 130, 44]).every(isBigEnough);   // false
    new Uint8Array([12, 54, 18, 130, 44]).every(isBigEnough); // true

### Testing typed array elements using arrow functions

[Arrow functions](../../functions/arrow_functions) provide a shorter syntax for the same test.

    new Uint8Array([12, 5, 8, 130, 44]).every(elem => elem >= 10); // false
    new Uint8Array([12, 54, 18, 130, 44]).every(elem => elem >= 10); // true

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="#">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-%typedarray%.prototype.every</span></a></td></tr></tbody></table>

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

`every`

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

-   [`TypedArray.prototype.some()`](some)
-   [`Array.prototype.every()`](../array/every)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/every" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/every</a>
