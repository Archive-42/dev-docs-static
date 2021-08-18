get ArrayBuffer\[@@species\]
============================

The `ArrayBuffer[@@species]` accessor property returns the `ArrayBuffer` constructor.

Description
-----------

The species accessor property returns the default constructor for `ArrayBuffer` objects. Subclass constructors may over-ride it to change the constructor assignment.

Examples
--------

### Species in ordinary objects

The species property returns the default constructor function, which is the `ArrayBuffer` constructor for `ArrayBuffer` objects:

    ArrayBuffer[Symbol.species]; // function ArrayBuffer()

### Species in derived objects

In a derived collection object (e.g. your custom array buffer `MyArrayBuffer`), the `MyArrayBuffer` species is the `MyArrayBuffer` constructor. However, you might want to overwrite this, in order to return parent `ArrayBuffer` objects in your derived class methods:

    class MyArrayBuffer extends ArrayBuffer {
      // Overwrite MyArrayBuffer species to the parent ArrayBuffer constructor
      static get [Symbol.species]() { return ArrayBuffer; }
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-get-arraybuffer-@@species">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-get-arraybuffer-@@species</span></a></td></tr></tbody></table>

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

-   [`ArrayBuffer`](../arraybuffer)
-   [`Symbol.species`](../symbol/species)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer/@@species" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer/@@species</a>
