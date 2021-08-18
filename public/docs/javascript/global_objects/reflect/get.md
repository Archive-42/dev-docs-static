Reflect.get()
=============

The static `Reflect.get()` method works like getting a property from an object (`target[propertyKey]`) as a function.

Syntax
------

    Reflect.get(target, propertyKey)
    Reflect.get(target, propertyKey, receiver)

### Parameters

`target`  
The target object on which to get the property.

`propertyKey`  
The name of the property to get.

 `receiver` <span class="badge inline optional">Optional</span>   
The value of `this` provided for the call to `target` if a getter is encountered. When used with [`Proxy`](../proxy), it can be an object that inherits from `target`.

### Return value

The value of the property.

### Exceptions

A [`TypeError`](../typeerror), if `target` is not an [`Object`](../object).

Description
-----------

The `Reflect.get` method allows you to get a property on an object. It is like the [property accessor](../../operators/property_accessors) syntax as a function.

Examples
--------

### Using `Reflect.get()`

    // Object
    let obj = { x: 1, y: 2 }
    Reflect.get(obj, 'x')  // 1

    // Array
    Reflect.get(['zero', 'one'], 1)  // "one"

    // Proxy with a get handler
    let x = {p: 1};

    let obj = new Proxy(x, {
      get(t, k, r) {
        return k + 'bar'
      }
    })
    Reflect.get(obj, 'foo')  // "foobar"

    //Proxy with get handler and receiver
    let x = {p: 1, foo: 2};
    let y = {foo: 3};

    let obj = new Proxy(x, {
      get(t, prop, receiver) {
        return receiver[prop] + 'bar'
      }
    })
    Reflect.get(obj, 'foo', y) // "3bar"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-reflect.get">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-reflect.get</span></a></td></tr></tbody></table>

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

`get`

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
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/get" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/get</a>
