Reflect.setPrototypeOf()
========================

The static `Reflect.setPrototypeOf()` method is the same method as [`Object.setPrototypeOf()`](../object/setprototypeof), except for its return type. It sets the prototype (i.e., the internal `[[Prototype]]` property) of a specified object to another object or to [`null`](../null), and returns `true` if the operation was successful, or `false` otherwise.

Syntax
------

    Reflect.setPrototypeOf(target, prototype)

### Parameters

`target`  
The target object of which to set the prototype.

`prototype`  
The object's new prototype (an object or [`null`](../null)).

### Return value

A [`Boolean`](../boolean) indicating whether or not the prototype was successfully set.

### Exceptions

A [`TypeError`](../typeerror), if `target` is not an [`Object`](../object) or if `prototype` is neither an object nor [`null`](../null).

Description
-----------

The `Reflect.setPrototypeOf` method changes the prototype (i.e. the value of the internal `[[Prototype]]` property) of the specified object.

Examples
--------

### Using Reflect.setPrototypeOf()

    Reflect.setPrototypeOf({}, Object.prototype)  // true

    // It can change an object's [[Prototype]] to null.
    Reflect.setPrototypeOf({}, null)  // true

    // Returns false if target is not extensible.
    Reflect.setPrototypeOf(Object.freeze({}), null)  // false

    // Returns false if it cause a prototype chain cycle.
    let target = {}
    let proto = Object.create(target)
    Reflect.setPrototypeOf(target, proto)  // false

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-reflect.setprototypeof">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-reflect.setprototypeof</span></a></td></tr></tbody></table>

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

`setPrototypeOf`

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
-   [`Object.setPrototypeOf()`](../object/setprototypeof)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/setPrototypeOf" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/setPrototypeOf</a>
