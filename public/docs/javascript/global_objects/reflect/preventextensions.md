Reflect.preventExtensions()
===========================

The static `Reflect.preventExtensions()` method prevents new properties from ever being added to an object (i.e., prevents future extensions to the object). It is similar to [`Object.preventExtensions()`](../object/preventextensions), but with some [differences](#difference_from_object.preventextensions).

Syntax
------

    Reflect.preventExtensions(target)

### Parameters

`target`  
The target object on which to prevent extensions.

### Return value

A [`Boolean`](../boolean) indicating whether or not the target was successfully set to prevent extensions.

### Exceptions

A [`TypeError`](../typeerror), if `target` is not an [`Object`](../object).

Description
-----------

The `Reflect.preventExtensions()` method allows you to prevent new properties from ever being added to an object (i.e., prevents future extensions to the object). It is similar to [`Object.preventExtensions()`](../object/preventextensions).

Examples
--------

### Using Reflect.preventExtensions()

See also [`Object.preventExtensions()`](../object/preventextensions).

    // Objects are extensible by default.
    let empty = {}
    Reflect.isExtensible(empty)  // === true

    // ...but that can be changed.
    Reflect.preventExtensions(empty)
    Reflect.isExtensible(empty)  // === false

### Difference from Object.preventExtensions()

If the `target` argument to this method is not an object (a primitive), then it will cause a [`TypeError`](../typeerror). With [`Object.preventExtensions()`](../object/preventextensions), a non-object `target` will be coerced to an object.

    Reflect.preventExtensions(1)
    // TypeError: 1 is not an object

    Object.preventExtensions(1)
    // 1

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-reflect.preventextensions">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-reflect.preventextensions</span></a></td></tr></tbody></table>

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

`preventExtensions`

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
-   [`Object.isExtensible()`](../object/isextensible)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/preventExtensions" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/preventExtensions</a>
