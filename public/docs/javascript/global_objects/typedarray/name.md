TypedArray.name
===============

The `TypedArray.name` property represents a string value of the typed array constructor name.

Property attributes of `TypedArray.name`

Writable

no

Enumerable

no

Configurable

no

Description
-----------

`TypedArray` objects differ from each other in the number of bytes per element and in the way the bytes are interpreted. The `name` property describes of what data type the array consists. The first part can be `Int` for "integer" or `Uint` for an "unsigned integer", also `Float` for "floating point" is used. The second part is a number describing the bit-size of the array. Finally, the object type is `Array`, with `ClampedArray` as a special case. Please see [`Uint8ClampedArray`](../uint8clampedarray) for more details.

Examples
--------

### Using name

    Int8Array.name;         // "Int8Array"
    Uint8Array.name;        // "Uint8Array"
    Uint8ClampedArray.name; // "Uint8ClampedArray"
    Int16Array.name;        // "Int16Array"
    Uint16Array.name;       // "Uint16Array"
    Int32Array.name;        // "Int32Array"
    Uint32Array.name;       // "Uint32Array"
    Float32Array.name;      // "Float32Array"
    Float64Array.name;      // "Float64Array"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-properties-of-the-typedarray-constructors">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-properties-of-the-typedarray-constructors</span></a></td></tr></tbody></table>

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

`name`

7

12

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
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/name" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/name</a>
