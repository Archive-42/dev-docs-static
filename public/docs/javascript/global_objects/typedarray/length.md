TypedArray.prototype.length
===========================

The `length` accessor property represents the length (in elements) of a typed array.

Description
-----------

The `length` property is an accessor property whose set accessor function is `undefined`, meaning that you can only read this property. The value is established when a *TypedArray* is constructed and cannot be changed. If the *TypedArray* is not specifying a `byteOffset` or a `length`, the length of the referenced [`ArrayBuffer`](../arraybuffer) will be returned. *TypedArray* is one of the [TypedArray objects](../typedarray#typedarray_objects).

Examples
--------

### Using the `length` property

    var buffer = new ArrayBuffer(8);

    var uint8 = new Uint8Array(buffer);
    uint8.length; // 8 (matches the length of the buffer)

    var uint8 = new Uint8Array(buffer, 1, 5);
    uint8.length; // 5 (as specified when constructing the Uint8Array)

    var uint8 = new Uint8Array(buffer, 2);
    uint8.length; // 6 (due to the offset of the constructed Uint8Array)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="#">ECMAScript (ECMA-262)<br />
<span class="small">The definition of 'TypedArray.prototype.length' in that specification.</span></a></td></tr></tbody></table>

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

`length`

7

14

4

10

11.6

5.1

4

18

4

12

4.2

1.0

See also
--------

-   [JavaScript typed arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Typed_arrays)
-   [`TypedArray`](../typedarray)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/length" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/length</a>
