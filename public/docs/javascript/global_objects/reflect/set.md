Reflect.set()
=============

The static `Reflect.set()` method works like setting a property on an object.

Syntax
------

    Reflect.set(target, propertyKey, value)
    Reflect.set(target, propertyKey, value, receiver)

### Parameters

`target`  
The target object on which to set the property.

`propertyKey`  
The name of the property to set.

`value`  
The value to set.

 `receiver` <span class="badge inline optional">Optional</span>   
The value of `this` provided for the call to `target` if a setter is encountered.

### Return value

A [`Boolean`](../boolean) indicating whether or not setting the property was successful.

### Exceptions

A [`TypeError`](../typeerror), if `target` is not an [`Object`](../object).

Description
-----------

The `Reflect.set` method allows you to set a property on an object. It does property assignment and is like the [property accessor](../../operators/property_accessors) syntax as a function.

Examples
--------

### Using Reflect.set()

    // Object
    let obj = {}
    Reflect.set(obj, 'prop', 'value')  // true
    obj.prop  // "value"

    // Array
    let arr = ['duck', 'duck', 'duck']
    Reflect.set(arr, 2, 'goose')  // true
    arr[2]  // "goose"

    // It can truncate an array.
    Reflect.set(arr, 'length', 1)  // true
    arr  // ["duck"]

    // With just one argument, propertyKey and value are "undefined".
    let obj = {}
    Reflect.set(obj)  // true
    Reflect.getOwnPropertyDescriptor(obj, 'undefined')
    // { value: undefined, writable: true, enumerable: true, configurable: true }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-reflect.set">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-reflect.set</span></a></td></tr></tbody></table>

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

`set`

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
-   [Property accessors](../../operators/property_accessors)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/set" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/set</a>
