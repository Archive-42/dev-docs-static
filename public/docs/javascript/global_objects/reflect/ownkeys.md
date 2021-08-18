Reflect.ownKeys()
=================

The static `Reflect.ownKeys()` method returns an array of the `target` object's own property keys.

Syntax
------

    Reflect.ownKeys(target)

### Parameters

`target`  
The target object from which to get the own keys.

### Return value

An [`Array`](../array) of the `target` object's own property keys.

### Exceptions

A [`TypeError`](../typeerror), if `target` is not an [`Object`](../object).

Description
-----------

The `Reflect.ownKeys` method returns an array of the `target` object's own property keys. Its return value is equivalent to `Object.getOwnPropertyNames(target).concat(Object.getOwnPropertySymbols(target))`.

Examples
--------

### Using Reflect.ownKeys()

    Reflect.ownKeys({z: 3, y: 2, x: 1})  // [ "z", "y", "x" ]
    Reflect.ownKeys([])                  // ["length"]

    let sym = Symbol.for('comet')
    let sym2 = Symbol.for('meteor')
    let obj = {[sym]: 0, 'str': 0, '773': 0, '0': 0,
               [sym2]: 0, '-1': 0, '8': 0, 'second str': 0}
    Reflect.ownKeys(obj)
    // [ "0", "8", "773", "str", "-1", "second str", Symbol(comet), Symbol(meteor) ]
    // Indexes in numeric order,
    // strings in insertion order,
    // symbols in insertion order

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-reflect.ownkeys">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-reflect.ownkeys</span></a></td></tr></tbody></table>

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

`ownKeys`

49

12

42

No

36

10

49

49

42

36

10

5.0

See also
--------

-   [`Reflect`](../reflect)
-   [`Object.getOwnPropertyNames()`](../object/getownpropertynames)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/ownKeys" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/ownKeys</a>
