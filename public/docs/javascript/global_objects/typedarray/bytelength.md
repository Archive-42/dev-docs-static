TypedArray.prototype.byteLength
===============================

The `byteLength` accessor property represents the length (in bytes) of a typed array.

Description
-----------

The `byteLength` property is an accessor property whose set accessor function is `undefined`, meaning that you can only read this property. The value is established when a *TypedArray* is constructed and cannot be changed. If the *TypedArray* is not specifying a `byteOffset` or a `length`, the `length` of the referenced `ArrayBuffer` will be returned. *TypedArray* is one of the [TypedArray objects](../typedarray#typedarray_objects).

Examples
--------

### Using the byteLength property

    var buffer = new ArrayBuffer(8);

    var uint8 = new Uint8Array(buffer);
    uint8.byteLength; // 8 (matches the byteLength of the buffer)

    var uint8 = new Uint8Array(buffer, 1, 5);
    uint8.byteLength; // 5 (as specified when constructing the Uint8Array)

    var uint8 = new Uint8Array(buffer, 2);
    uint8.byteLength; // 6 (due to the offset of the constructed Uint8Array)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="#">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-get-%typedarray%.prototype.bytelength</span></a></td></tr></tbody></table>

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

`byteLength`

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
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/byteLength" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/byteLength</a>
