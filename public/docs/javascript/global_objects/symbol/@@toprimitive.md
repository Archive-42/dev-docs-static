Symbol.prototype\[@@toPrimitive\]
=================================

The `[@@toPrimitive]()` method converts a Symbol object to a primitive value.

Syntax
------

    Symbol()[Symbol.toPrimitive](hint)

### Return value

The primitive value of the specified [`Symbol`](../symbol) object.

Description
-----------

The `[@@toPrimitive]()` method of [`Symbol`](../symbol) returns the primitive value of a Symbol object as a Symbol data type. The `hint` argument is not used.

JavaScript calls the `[@@toPrimitive]()` method to convert an object to a primitive value. You rarely need to invoke the `[@@toPrimitive]()` method yourself; JavaScript automatically invokes it when encountering an object where a primitive value is expected.

Examples
--------

### Using @@toPrimitive

    const sym = Symbol("example");
    sym === sym[Symbol.toPrimitive](); // true

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-symbol.prototype-@@toprimitive">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-symbol.prototype-@@toprimitive</span></a></td></tr></tbody></table>

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

`@@toPrimitive`

47

15

44

No

34

10

47

47

44

34

10

5.0

See also
--------

-   [`Symbol.toPrimitive`](toprimitive)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/@@toPrimitive" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/@@toPrimitive</a>
