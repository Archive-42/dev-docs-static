Reflect.has()
=============

The static `Reflect.has()` method works like the [`in` operator](../../operators/in) as a function.

Syntax
------

    Reflect.has(target, propertyKey)

### Parameters

`target`  
The target object in which to look for the property.

`propertyKey`  
The name of the property to check.

### Return value

A [`Boolean`](../boolean) indicating whether or not the `target` has the property.

### Exceptions

A [`TypeError`](../typeerror), if `target` is not an [`Object`](../object).

Description
-----------

The `Reflect.has` method allows you to check if a property is in an object. It works like the [`in` operator](../../operators/in) as a function.

Examples
--------

### Using Reflect.has()

    Reflect.has({x: 0}, 'x')  // true
    Reflect.has({x: 0}, 'y')  // false

    // returns true for properties in the prototype chain
    Reflect.has({x: 0}, 'toString')

    // Proxy with .has() handler method
    obj = new Proxy({}, {
      has(t, k) { return k.startsWith('door')  }
    });
    Reflect.has(obj, 'doorbell')  // true
    Reflect.has(obj, 'dormitory')  // false

`Reflect.has` returns `true` for any inherited properties, like the [`in` operator](../../operators/in):

    const a = {foo: 123}
    const b = {__proto__: a}
    const c = {__proto__: b}
    // The prototype chain is: c -> b -> a
    Reflect.has(c, 'foo') // true

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-reflect.has">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-reflect.has</span></a></td></tr></tbody></table>

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

`has`

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
-   [`in` operator](../../operators/in)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/has" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/has</a>
