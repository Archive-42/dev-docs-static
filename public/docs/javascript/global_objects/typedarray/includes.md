TypedArray.prototype.includes()
===============================

The `includes()` method determines whether a typed array includes a certain element, returning `true` or `false` as appropriate. This method has the same algorithm as [`Array.prototype.includes()`](../array/includes). *TypedArray* is one of the [typed array types](../typedarray#typedarray_objects) here.

Syntax
------

    includes(searchElement)
    includes(searchElement, fromIndex)

### Parameters

`searchElement`  
The element to search for.

 `fromIndex` <span class="badge inline optional">Optional</span>   
The position in this array at which to begin searching for `searchElement`; defaults to 0.

### Return value

A [`Boolean`](../boolean).

Examples
--------

### Using includes

    var uint8 = new Uint8Array([1,2,3]);
    uint8.includes(2);     // true
    uint8.includes(4);     // false
    uint8.includes(3, 3);  // false

    // NaN handling (only true for Float32 and Float64)
    new Uint8Array([NaN]).includes(NaN); // false, since the NaN passed to the constructor gets converted to 0
    new Float32Array([NaN]).includes(NaN); // true;
    new Float64Array([NaN]).includes(NaN); // true;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="#">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-%typedarray%.prototype.includes</span></a></td></tr></tbody></table>

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

`includes`

47

14

43

No

34

10

No

47

43

34

10

5.0

See also
--------

-   [`Array.prototype.includes()`](../array/includes)
-   [`String.prototype.includes()`](../string/includes)
-   [`TypedArray.prototype.indexOf()`](indexof)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/includes" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/includes</a>
