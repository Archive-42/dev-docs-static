Reflect.defineProperty()
========================

The static `Reflect.defineProperty()` method is like [`Object.defineProperty()`](../object/defineproperty) but returns a [`Boolean`](../boolean).

Syntax
------

    Reflect.defineProperty(target, propertyKey, attributes)

### Parameters

`target`  
The target object on which to define the property.

`propertyKey`  
The name of the property to be defined or modified.

`attributes`  
The attributes for the property being defined or modified.

### Return value

A [`Boolean`](../boolean) indicating whether or not the property was successfully defined.

### Exceptions

A [`TypeError`](../typeerror), if `target` is not an [`Object`](../object).

Description
-----------

The `Reflect.defineProperty` method allows precise addition to or modification of a property on an object. For more details, see the [`Object.defineProperty`](../object/defineproperty) which is similar.

**Note:** `Object.defineProperty` returns the object or throws a [`TypeError`](../typeerror) if the property has not been successfully defined. `Reflect.defineProperty`, however, returns a [`Boolean`](../boolean) indicating whether or not the property was successfully defined.

Examples
--------

### Using Reflect.defineProperty()

    let obj = {}
    Reflect.defineProperty(obj, 'x', {value: 7})  // true
    obj.x                                         // 7

### Checking if property definition has been successful

With [`Object.defineProperty`](../object/defineproperty), which returns an object if successful, or throws a [`TypeError`](../typeerror) otherwise, you would use a `try...catch` block to catch any error that occurred while defining a property.

Because `Reflect.defineProperty` returns a Boolean success status, you can just use an `if...else` block here:

    if (Reflect.defineProperty(target, property, attributes)) {
      // success
    } else {
      // failure
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-reflect.defineproperty">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-reflect.defineproperty</span></a></td></tr></tbody></table>

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

`defineProperty`

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
-   [`Object.defineProperty()`](../object/defineproperty)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/defineProperty" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/defineProperty</a>
