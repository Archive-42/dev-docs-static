TypedArray.prototype.fill()
===========================

The `fill()` method fills all the elements of a typed array from a start index to an end index with a static value. This method has the same algorithm as [`Array.prototype.fill()`](../array/fill). *TypedArray* is one of the [typed array types](../typedarray#typedarray_objects) here.

Syntax
------

    fill(value)
    fill(value, start)
    fill(value, start, end)

### Parameters

`value`  
Value to fill the typed array with.

 `start` <span class="badge inline optional">Optional</span>   
Start index. Defaults to 0.

 `end` <span class="badge inline optional">Optional</span>   
End index (not included). Defaults to `this.length`.

### Return value

The modified array.

Description
-----------

The elements interval to fill is \[`start`, `end`).

The `fill()` method takes up to three arguments `value`, `start``start` and `end`. The `start` and `end` arguments are optional with default values of `0` and the `length` of the `this` object.

If `start` is negative, it is treated as `length+start` where `length` is the length of the array. If `end` is negative, it is treated as `length+end`.

Examples
--------

### Using fill()

    new Uint8Array([1, 2, 3]).fill(4);         // Uint8Array [4, 4, 4]
    new Uint8Array([1, 2, 3]).fill(4, 1);      // Uint8Array [1, 4, 4]
    new Uint8Array([1, 2, 3]).fill(4, 1, 2);   // Uint8Array [1, 4, 3]
    new Uint8Array([1, 2, 3]).fill(4, 1, 1);   // Uint8Array [1, 2, 3]
    new Uint8Array([1, 2, 3]).fill(4, -3, -2); // Uint8Array [4, 2, 3]

Polyfill
--------

Since there is no global object with the name *TypedArray*, polyfilling must be done on an "as needed" basis. Use the following "polyfill" along with the [`Array.prototype.fill()`](../array/fill) polyfill.

    // https://tc39.github.io/ecma262/#sec-%typedarray%.prototype.fill
    if (!Uint8Array.prototype.fill) {
      Uint8Array.prototype.fill = Array.prototype.fill;
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="#">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-%typedarray%.prototype.fill</span></a></td></tr></tbody></table>

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

`fill`

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

-   [`Array.prototype.fill()`](../array/fill)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/fill" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/fill</a>
