Reflect.getOwnPropertyDescriptor()
==================================

The static `Reflect.getOwnPropertyDescriptor()` method is similar to [`Object.getOwnPropertyDescriptor()`](../object/getownpropertydescriptor). It returns a property descriptor of the given property if it exists on the object, [`undefined`](../undefined) otherwise.

Syntax
------

    Reflect.getOwnPropertyDescriptor(target, propertyKey)

### Parameters

`target`  
The target object in which to look for the property.

`propertyKey`  
The name of the property to get an own property descriptor for.

### Return value

A property descriptor object if the property exists in `target` object; otherwise, [`undefined`](../undefined).

### Exceptions

A [`TypeError`](../typeerror), if `target` is not an [`Object`](../object).

Description
-----------

The `Reflect.getOwnPropertyDescriptor` method returns a property descriptor of the given property if it exists in the `target` object, [`undefined`](../undefined) otherwise. The only difference to [`Object.getOwnPropertyDescriptor()`](../object/getownpropertydescriptor) is how non-object targets are handled.

Examples
--------

### Using Reflect.getOwnPropertyDescriptor()

    Reflect.getOwnPropertyDescriptor({x: 'hello'}, 'x')
    // {value: "hello", writable: true, enumerable: true, configurable: true}

    Reflect.getOwnPropertyDescriptor({x: 'hello'}, 'y')
    // undefined

    Reflect.getOwnPropertyDescriptor([], 'length')
    // {value: 0, writable: true, enumerable: false, configurable: false}

### Difference to Object.getOwnPropertyDescriptor()

If the `target` argument to this method is not an object (a primitive), then it will cause a [`TypeError`](../typeerror). With [`Object.getOwnPropertyDescriptor`](../object/getownpropertydescriptor), a non-object first argument will be coerced to an object at first.

    Reflect.getOwnPropertyDescriptor('foo', 0)
    // TypeError: "foo" is not non-null object

    Object.getOwnPropertyDescriptor('foo', 0)
    // { value: "f", writable: false, enumerable: true, configurable: false }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-reflect.getownpropertydescriptor">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-reflect.getownpropertydescriptor</span></a></td></tr></tbody></table>

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

`getOwnPropertyDescriptor`

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
-   [`Object.getOwnPropertyDescriptor()`](../object/getownpropertydescriptor)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/getOwnPropertyDescriptor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/getOwnPropertyDescriptor</a>
