Reflect.deleteProperty()
========================

The static `Reflect``.deleteProperty()` method allows to delete properties. It is like the [`delete` operator](../../operators/delete) as a function.

Syntax
------

    Reflect.deleteProperty(target, propertyKey)

### Parameters

`target`  
The target object on which to delete the property.

`propertyKey`  
The name of the property to be deleted.

### Return value

A [`Boolean`](../boolean) indicating whether or not the property was successfully deleted.

### Exceptions

A [`TypeError`](../typeerror), if `target` is not an [`Object`](../object).

Description
-----------

The `Reflect.deleteProperty` method allows you to delete a property on an object. It returns a [`Boolean`](../boolean) indicating whether or not the property was successfully deleted. It is almost identical to the non-strict [`delete` operator](../../operators/delete).

Examples
--------

### Using `Reflect.deleteProperty()`

    let obj = { x: 1, y: 2 }
    Reflect.deleteProperty(obj, 'x')  // true
    obj                               // { y: 2 }

    let arr = [1, 2, 3, 4, 5]
    Reflect.deleteProperty(arr, '3')  // true
    arr                               // [1, 2, 3, undefined, 5]

    // Returns true if no such property exists
    Reflect.deleteProperty({}, 'foo')  // true

    // Returns false if a property is unconfigurable
    Reflect.deleteProperty(Object.freeze({foo: 1}), 'foo')  // false

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-reflect.deleteproperty">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-reflect.deleteproperty</span></a></td></tr></tbody></table>

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

`deleteProperty`

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
-   [`delete` operator](../../operators/delete)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/deleteProperty" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/deleteProperty</a>
