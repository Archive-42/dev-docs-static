TypedArray.prototype.at()
=========================

The `at()` method takes an integer value and returns the item at that index, allowing for positive and negative integers. Negative integers count back from the last item in the array.

This is not to suggest there is anything wrong with using the square bracket notation. For example `array[0]` would return the first item. However instead of using [`array.length`](length) for latter items; e.g. `array[array.length-1]` for the last item, you can call `array.at(-1)`. [(See the examples below)](#examples)

Syntax
------

    at(index)

### Parameters

`index`  
The index (position) of the array element to be returned. Supports relative indexing from the end of the array when passed a negative index. i.e. If a negative number is used the element returned will be found by counting back from the end of the array.

### Return value

The element in the array matching the given index. Returns [`undefined`](../undefined) if the given index can not be found.

Examples
--------

### Return the last value of a typed array

The following example provides a function which returns the last element found in a specified array.

    const uint8 = new Uint8Array([1, 2, 4, 7, 11, 18]);

    // A function which returns the last item of a given array
    function returnLast(arr) {
      return arr.at(-1);
    }

    const lastItem = returnLast(uint8);
    console.log(lastItem); // Logs: 18

### Comparing methods

Here we compare different ways to select the penultimate (last but one) item of a [`TypedArray`](../typedarray). Whilst all below methods are valid, it highlights the succinctness and readability of the `at()` method.

    // Our typed array with values
    const uint8 = new Uint8Array([1, 2, 4, 7, 11, 18]);

    // Using length property
    const lengthWay = uint8[uint8.length-2];
    console.log(lengthWay); // Logs: 11

    // Using slice() method. Note an array is returned
    const sliceWay = uint8.slice(-2, -1);
    console.log(sliceWay[0]); // Logs: 11

    // Using at() method
    const atWay = uint8.at(-2);
    console.log(atWay); // Logs: 11

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="#">Relative Indexing Method (Relative Indexing Method)<br />
<span class="small">#sec-%typedarray.prototype%-additions</span></a></td></tr></tbody></table>

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

`at`

No

No

No

No

No

No

No

No

No

No

No

No

See also
--------

-   [A polyfill for the at() method](https://github.com/tc39/proposal-relative-indexing-method#polyfill).
-   [`TypedArray.prototype.find()`](find) – return a value based on a given test.
-   [`TypedArray.prototype.includes()`](includes) – test whether a value exists in the array.
-   [`TypedArray.prototype.indexOf()`](indexof) – return the index of a given element.

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/at" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/at</a>
