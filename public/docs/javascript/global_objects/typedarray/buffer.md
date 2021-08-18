TypedArray.prototype.buffer
===========================

The `buffer` accessor property represents the [`ArrayBuffer`](../arraybuffer) referenced by a *TypedArray* at construction time.

Description
-----------

The `buffer` property is an accessor property whose set accessor function is `undefined`, meaning that you can only read this property. The value is established when the *TypedArray* is constructed and cannot be changed. *TypedArray* is one of the [TypedArray objects](../typedarray#typedarray_objects).

Examples
--------

### Using the buffer property

    var buffer = new ArrayBuffer(8);
    var uint16 = new Uint16Array(buffer);
    uint16.buffer; // ArrayBuffer { byteLength: 8 }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="#">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-get-%typedarray%.prototype.buffer</span></a></td></tr></tbody></table>

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

`buffer`

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
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/buffer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/buffer</a>
