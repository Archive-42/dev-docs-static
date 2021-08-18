get TypedArray\[@@species\]
===========================

The `TypedArray[@@species]` accessor property returns the constructor of a [typed array](../typedarray#typedarray_objects).

Description
-----------

The `species` accessor property returns the default constructor for [typed array](../typedarray#typedarray_objects) objects. Subclass constructors may over-ride it to change the constructor assignment.

Examples
--------

### Species in ordinary objects

The `species` property returns the default constructor function, which is one of the typed array constructors for a given [typed array](../typedarray#typedarray_objects) object:

    Int8Array[Symbol.species];    // function Int8Array()
    Uint8Array[Symbol.species];   // function Uint8Array()
    Float32Array[Symbol.species]; // function Float32Array()

### Species in derived objects

In a derived collection object (e.g. your custom typed array `MyTypedArray`), the `MyTypedArray` species is the `MyTypedArray` constructor. However, you might want to overwrite this, in order to return a parent [typed array](../typedarray#typedarray_objects) object in your derived class methods:

    class MyTypedArray extends Uint8Array {
      // Overwrite MyTypedArray species to the parent Uint8Array constructor
      static get [Symbol.species]() { return Uint8Array; }
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="#">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-get-%typedarray%-@@species</span></a></td></tr></tbody></table>

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

`@@species`

51

13

48

No

38

10

51

51

48

41

10

5.0

See also
--------

-   [`TypedArray`](../typedarray)
-   [`Symbol.species`](../symbol/species)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/@@species" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/@@species</a>
