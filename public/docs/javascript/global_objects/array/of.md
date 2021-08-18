Array.of()
==========

The `Array.of()` method creates a new `Array` instance from a variable number of arguments, regardless of number or type of the arguments.

The difference between `Array.of()` and the `Array` constructor is in the handling of integer arguments: `Array.of(7)` creates an array with a single element, `7`, whereas `Array(7)` creates an empty array with a `length` property of `7` (**Note:** this implies an array of `7` empty slots, not slots with actual [`undefined`](../undefined) values).

    Array.of(7); // [7]
    Array(7); // array of 7 empty slots

    Array.of(1, 2, 3); // [1, 2, 3]
    Array(1, 2, 3);    // [1, 2, 3]

Syntax
------

    Array.of(element0)
    Array.of(element0, element1)
    Array.of(element0, element1, ... , elementN)

### Parameters

`elementN`  
Elements used to create the array.

### Return value

A new [`Array`](../array) instance.

Description
-----------

This function is part of the ECMAScript 2015 standard.

For more information, see:

-   [`Array.of()`](https://gist.github.com/rwaldron/1074126)
-   [`Array.from()` proposal](https://gist.github.com/rwaldron/1074126)
-   [`Array.of()` polyfill](https://gist.github.com/rwaldron/3186576)

Examples
--------

### Using Array.of

    Array.of(1);         // [1]
    Array.of(1, 2, 3);   // [1, 2, 3]
    Array.of(undefined); // [undefined]

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-array.of">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-array.of</span></a></td></tr></tbody></table>

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

`of`

45

12

25

No

26

9

39

39

25

26

9

4.0

See also
--------

-   [A polyfill](https://github.com/behnammodi/polyfill/blob/master/array.polyfill.js)
-   [`Array`](../array)
-   [`Array.from()`](from)
-   [`TypedArray.of()`](../typedarray/of)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/of" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/of</a>
