get Set\[@@species\]
====================

The `Set[Symbol.species]` accessor property returns the `Set` constructor.

Description
-----------

The `species` accessor property returns the default constructor for `Set` objects. Subclass constructors may override it to change the constructor assignment.

Examples
--------

### Species in ordinary objects

The `species` property returns the default constructor function, which is the `Set` constructor for `Set` objects:

    Set[Symbol.species]; // function Set()

### Species in derived objects

In a derived collection object (e.g. your custom set `MySet`), the `MySet` species is the `MySet` constructor. However, you might want to overwrite this, in order to return parent `Set` objects in your derived class methods:

    class MySet extends Set {
      // Overwrite MySet species to the parent Set constructor
      static get [Symbol.species]() { return Set; }
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-get-set-@@species">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-get-set-@@species</span></a></td></tr></tbody></table>

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

41

No

38

10

51

51

41

41

10

5.0

See also
--------

-   [`Set`](../set)
-   [`Symbol.species`](../symbol/species)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/@@species" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/@@species</a>
