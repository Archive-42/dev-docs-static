get Array\[@@species\]
======================

The `Array[@@species]` accessor property returns the `Array` constructor.

Syntax
------

    Array[Symbol.species]

### Return value

The [`Array`](../array) constructor.

Description
-----------

The `species` accessor property returns the default constructor for `Array` objects. Subclass constructors may override it to change the constructor assignment.

Examples
--------

### Species in ordinary objects

The `species` property returns the default constructor function, which is the `Array` constructor for `Array` objects:

    Array[Symbol.species]; // function Array()

### Species in derived objects

In a derived collection object (e.g. your custom array `MyArray`), the `MyArray` species is the `MyArray` constructor. However, you might want to overwrite this, in order to return parent `Array` objects in your derived class methods:

    class MyArray extends Array {
      // Overwrite MyArray species to the parent Array constructor
      static get [Symbol.species]() { return Array; }
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-get-array-@@species">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-get-array-@@species</span></a></td></tr></tbody></table>

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

79

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

-   [`Array`](../array)
-   [`Symbol.species`](../symbol/species)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/@@species" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/@@species</a>
