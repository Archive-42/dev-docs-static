Symbol() constructor
====================

The `Symbol()` constructor returns a value of type **symbol**, but is incomplete as a constructor because it does not support the syntax "`new Symbol()`" and it is not intended to be subclassed. It may be used as the value of an `extends` clause of a `class` definition but a `super` call to it will cause an exception.

Syntax
------

    Symbol()
    Symbol(description)

### Parameters

 `description` <span class="badge inline optional">Optional</span>   
A string. A description of the symbol which can be used for debugging but not to access the symbol itself.

Examples
--------

### Creating symbols

To create a new primitive symbol, you write `Symbol()` with an optional string as its description:

    let sym1 = Symbol()
    let sym2 = Symbol('foo')
    let sym3 = Symbol('foo')

The above code creates three new symbols. Note that `Symbol("foo")` does not coerce the string `"foo"` into a symbol. It creates a new symbol each time:

    Symbol('foo') === Symbol('foo')  // false

### new Symbol(...)

The following syntax with the [`new`](../../operators/new) operator will throw a [`TypeError`](../typeerror):

    let sym = new Symbol()  // TypeError

This prevents authors from creating an explicit `Symbol` wrapper object instead of a new symbol value and might be surprising as creating explicit wrapper objects around primitive data types is generally possible (for example, `new Boolean`, `new String` and `new Number`).

If you really want to create a `Symbol` wrapper object, you can use the `Object()` function:

    let sym    = Symbol('foo');
    let symObj = Object(sym);
    typeof sym    // => "symbol"
    typeof symObj // => "object"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-symbol-constructor">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-symbol-constructor</span></a></td></tr></tbody></table>

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

`Symbol`

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

-   [Glossary: Symbol data type](https://developer.mozilla.org/en-US/docs/Glossary/Symbol)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/Symbol" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/Symbol</a>
