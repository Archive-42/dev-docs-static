Symbol.prototype.valueOf()
==========================

The `valueOf()` method returns the primitive value of a Symbol object.

Syntax
------

    valueOf()

### Return value

The primitive value of the specified [`Symbol`](../symbol) object.

Description
-----------

The `valueOf()` method of [`Symbol`](../symbol) returns the primitive value of a Symbol object as a Symbol data type.

JavaScript calls the `valueOf()` method to convert an object to a primitive value. You rarely need to invoke the `valueOf()` method yourself; JavaScript automatically invokes it when encountering an object where a primitive value is expected.

Examples
--------

### Using valueOf()

    const sym = Symbol("example");
    sym === sym.valueOf(); // true

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-symbol.prototype.valueof">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-symbol.prototype.valueof</span></a></td></tr></tbody></table>

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

`valueOf`

38

12

36

No

25

9

38

38

36

25

9

3.0

See also
--------

-   [`Object.prototype.valueOf()`](../object/valueof)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/valueOf" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/valueOf</a>
