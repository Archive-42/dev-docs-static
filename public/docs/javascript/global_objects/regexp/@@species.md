get RegExp\[@@species\]
=======================

The `RegExp[@@species]` accessor property returns the `RegExp` constructor.

Description
-----------

The `species` accessor property returns the default constructor for `RegExp` objects. Subclass constructors may over-ride it to change the constructor assignment.

Examples
--------

### Species in ordinary objects

The `species` property returns the default constructor function, which is the `RegExp` constructor for `RegExp` objects:

    RegExp[Symbol.species]; // function RegExp()

### Species in derived objects

In a derived collection object (e.g. your custom regexp `MyRegExp`), the `MyRegExp` species is the `MyRegExp` constructor. However, you might want to overwrite this, in order to return parent `RegExp` objects in your derived class methods:

    class MyRegExp extends RegExp {
      // Overwrite MyRegExp species to the parent RegExp constructor
      static get [Symbol.species]() { return RegExp; }
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-get-regexp-@@species">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-get-regexp-@@species</span></a></td></tr></tbody></table>

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

50

13

49

No

37

10

50

50

49

37

10

5.0

See also
--------

-   [`RegExp`](../regexp)
-   [`Symbol.species`](../symbol/species)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/@@species" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/@@species</a>
