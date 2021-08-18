get Map\[@@species\]
====================

The `Map[@@species]` accessor property returns the `Map` constructor.

Description
-----------

The species accessor property returns the default constructor for `Map` objects. Subclass constructors may over-ride it to change the constructor assignment.

Examples
--------

### Species in ordinary objects

The species property returns the default constructor function, which is the `Map` constructor for `Map` objects:

    Map[Symbol.species]; // function Map()

### Species in derived objects

In a derived collection object (e.g. your custom map `MyMap`), the `MyMap` species is the `MyMap` constructor. However, you might want to overwrite this, in order to return parent `Map` objects in your derived class methods:

    class MyMap extends Map {
      // Overwrite MyMap species to the parent Map constructor
      static get [Symbol.species]() { return Map; }
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-get-map-@@species">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-get-map-@@species</span></a></td></tr></tbody></table>

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

-   [`Map`](../map)
-   [`Symbol.species`](../symbol/species)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/@@species" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/@@species</a>
