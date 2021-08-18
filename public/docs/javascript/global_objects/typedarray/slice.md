TypedArray.prototype.slice()
============================

The `slice()` method returns a new typed array (with a new underlying buffer), that contains a copy of a portion of the original typed array. This method has the same algorithm as [`Array.prototype.slice()`](../array/slice). *TypedArray* is one of the [typed array types](../typedarray#typedarray_objects) here.

Syntax
------

    slice()
    slice(start)
    slice(start, end)

### Parameters

 `start` <span class="badge inline optional">Optional</span>   
Zero-based index at which to begin extraction.

A negative index can be used, indicating an offset from the end of the sequence. `slice(-2)` extracts the last two elements in the sequence.

If `start` is undefined, `slice` begins from index `0`.

 `end` <span class="badge inline optional">Optional</span>   
Zero-based index *before* which to end extraction. `slice` extracts up to but not including `end`.

For example, `slice(1,4)` extracts the second element through the fourth element (elements indexed 1, 2, and 3).

A negative index can be used, indicating an offset from the end of the sequence. `slice(2,-1)` extracts the third element through the second-to-last element in the sequence.

If `end` is omitted, `slice` extracts through the end of the sequence (`typedarray.length`).

### Return value

A new typed array containing the extracted elements.

Description
-----------

The `slice` method does not alter. It returns a shallow copy of elements from the original typed array.

If a new element is added to either typed array, the other typed array is not affected.

Examples
--------

### Return a portion of an existing typed array

    const uint8 = new Uint8Array([1,2,3]);
    uint8.slice(1);   // Uint8Array [ 2, 3 ]
    uint8.slice(2);   // Uint8Array [ 3 ]
    uint8.slice(-2);  // Uint8Array [ 2, 3 ]
    uint8.slice(0,1); // Uint8Array [ 1 ]

Polyfill
--------

Since there is no global object with the name *TypedArray*, polyfilling must be done on an "as needed" basis.

    if (!Uint8Array.prototype.slice) {
      Object.defineProperty(Uint8Array.prototype, 'slice', {
        value: function (begin, end)
         {
            return new Uint8Array(Array.prototype.slice.call(this, begin, end));
         }
      });
    }

If you need to support truly obsolete JavaScript engines that don't support [`Object.defineProperty`](../object/defineproperty), it's best not to polyfill `Array.prototype` methods at all, as you can't make them non-enumerable.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="#">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-%typedarray%.prototype.slice</span></a></td></tr></tbody></table>

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

`slice`

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

-   [`Array.prototype.slice()`](../array/slice)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/slice" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/slice</a>
