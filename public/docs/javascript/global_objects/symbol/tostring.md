Symbol.prototype.toString()
===========================

The `toString()` method returns a string representing the specified [`Symbol`](../symbol) object.

Syntax
------

    toString()

### Return value

A string representing the specified [`Symbol`](../symbol) object.

Description
-----------

The [`Symbol`](../symbol) object overrides the `toString` method of the [`Object`](../object) object; it does not inherit [`Object.prototype.toString()`](../object/tostring). For `Symbol` objects, the `toString` method returns a string representation of the object.

### No string concatenation

While you can call `toString()` on Symbols, you cannot use string concatenation with them:

    Symbol('foo') + 'bar'        // TypeError: Can't convert symbol to string

Examples
--------

### Using toString()

    Symbol('desc').toString()    // "Symbol(desc)"

    // well-known symbols
    Symbol.iterator.toString()   // "Symbol(Symbol.iterator)

    // global symbols
    Symbol.for('foo').toString() // "Symbol(foo)"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-symbol.prototype.tostring">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-symbol.prototype.tostring</span></a></td></tr></tbody></table>

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

`toString`

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

-   [`Object.prototype.toString()`](../object/tostring)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/toString" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/toString</a>
