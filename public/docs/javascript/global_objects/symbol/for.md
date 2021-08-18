Symbol.for()
============

The `Symbol.for(key)` method searches for existing symbols in a runtime-wide symbol registry with the given key and returns it if found. Otherwise a new symbol gets created in the global symbol registry with this key.

Syntax
------

    Symbol.for(key);

### Parameters

`key`  
String, required. The key for the symbol (and also used for the description of the symbol).

### Return value

An existing symbol with the given key if found; otherwise, a new symbol is created and returned.

Description
-----------

In contrast to `Symbol()`, the `Symbol.for()` function creates a symbol available in a global symbol registry list. `Symbol.for()` does also not necessarily create a new symbol on every call, but checks first if a symbol with the given `key` is already present in the registry. In that case, that symbol is returned. If no symbol with the given key is found, `Symbol.for()` will create a new global symbol.

### Global symbol registry

The global symbol registry is a list with the following record structure and it is initialized empty:

<table><caption>A record in the global symbol registry</caption><thead><tr class="header"><th>Field name</th><th>Value</th></tr></thead><tbody><tr class="odd"><td>[[key]]</td><td>A string key used to identify a symbol.</td></tr><tr class="even"><td>[[symbol]]</td><td>A symbol that is stored globally.</td></tr></tbody></table>

Examples
--------

### Using Symbol.for()

    Symbol.for('foo'); // create a new global symbol
    Symbol.for('foo'); // retrieve the already created symbol

    // Same global symbol, but not locally
    Symbol.for('bar') === Symbol.for('bar'); // true
    Symbol('bar') === Symbol('bar'); // false

    // The key is also used as the description
    var sym = Symbol.for('mario');
    sym.toString(); // "Symbol(mario)"

To avoid name clashes with your global symbol keys and other (library code) global symbols, it might be a good idea to prefix your symbols:

    Symbol.for('mdn.foo');
    Symbol.for('mdn.bar');

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-symbol.for">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-symbol.for</span></a></td></tr></tbody></table>

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

`for`

40

12

36

No

27

9

40

40

36

27

9

4.0

See also
--------

-   [`Symbol.keyFor()`](keyfor)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/for" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/for</a>
