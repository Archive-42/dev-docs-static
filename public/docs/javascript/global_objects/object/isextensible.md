Object.isExtensible()
=====================

The `Object.isExtensible()` method determines if an object is extensible (whether it can have new properties added to it).

Syntax
------

    Object.isExtensible(obj)

### Parameters

`obj`  
The object which should be checked.

### Return value

A [`Boolean`](../boolean) indicating whether or not the given object is extensible.

Description
-----------

Objects are extensible by default: they can have new properties added to them, and (in engines that support [`__proto__`](proto)) their `__proto__` property can be modified. An object can be marked as non-extensible using [`Object.preventExtensions()`](preventextensions), [`Object.seal()`](seal), or [`Object.freeze()`](freeze).

Examples
--------

### Using Object.isExtensible

    // New objects are extensible.
    var empty = {};
    Object.isExtensible(empty); // === true

    // ...but that can be changed.
    Object.preventExtensions(empty);
    Object.isExtensible(empty); // === false

    // Sealed objects are by definition non-extensible.
    var sealed = Object.seal({});
    Object.isExtensible(sealed); // === false

    // Frozen objects are also by definition non-extensible.
    var frozen = Object.freeze({});
    Object.isExtensible(frozen); // === false

### Non-object coercion

In ES5, if the argument to this method is not an object (a primitive), then it will cause a [`TypeError`](../typeerror). In ES2015, a non-object argument will be treated as if it was a non-extensible ordinary object, return `false`.

    Object.isExtensible(1);
    // TypeError: 1 is not an object (ES5 code)

    Object.isExtensible(1);
    // false                         (ES2015 code)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-object.isextensible">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-object.isextensible</span></a></td></tr></tbody></table>

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

`isExtensible`

6

12

4

9

12

5.1

1

18

4

12

6

1.0

See also
--------

-   [`Object.preventExtensions()`](preventextensions)
-   [`Object.seal()`](seal)
-   [`Object.isSealed()`](issealed)
-   [`Object.freeze()`](freeze)
-   [`Object.isFrozen()`](isfrozen)
-   [`Reflect.isExtensible()`](../reflect/isextensible)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/isExtensible" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/isExtensible</a>
