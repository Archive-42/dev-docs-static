Reflect.getPrototypeOf()
========================

The static `Reflect.getPrototypeOf()` method is almost the same method as [`Object.getPrototypeOf()`](../object/getprototypeof). It returns the prototype (i.e. the value of the internal `[[Prototype]]` property) of the specified object.

Syntax
------

    Reflect.getPrototypeOf(target)

### Parameters

`target`  
The target object of which to get the prototype.

### Return value

The prototype of the given object. If there are no inherited properties, [`null`](../null) is returned.

### Exceptions

A [`TypeError`](../typeerror), if `target` is not an [`Object`](../object).

Description
-----------

The `Reflect.getPrototypeOf` method returns the prototype (i.e. the value of the internal `[[Prototype]]` property) of the specified object.

Examples
--------

### Using Reflect.getPrototypeOf()

    Reflect.getPrototypeOf({})                  // Object.prototype
    Reflect.getPrototypeOf(Object.prototype)    // null
    Reflect.getPrototypeOf(Object.create(null)) // null

### Compared to Object.getPrototypeOf()

    // Same result for Objects
    Object.getPrototypeOf({})   // Object.prototype
    Reflect.getPrototypeOf({})  // Object.prototype

    // Both throw in ES5 for non-Objects
    Object.getPrototypeOf('foo')   // Throws TypeError
    Reflect.getPrototypeOf('foo')  // Throws TypeError

    // In ES2015 only Reflect throws, Object coerces non-Objects
    Object.getPrototypeOf('foo')   // String.prototype
    Reflect.getPrototypeOf('foo')  // Throws TypeError

    // To mimic the Object ES2015 behavior you need to coerce
    Reflect.getPrototypeOf(Object('foo'))  // String.prototype

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-reflect.getprototypeof">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-reflect.getprototypeof</span></a></td></tr></tbody></table>

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

`getPrototypeOf`

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
-   [`Object.getPrototypeOf()`](../object/getprototypeof)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/getPrototypeOf" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/getPrototypeOf</a>
