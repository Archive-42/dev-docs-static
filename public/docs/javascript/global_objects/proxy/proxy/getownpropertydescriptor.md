handler.getOwnPropertyDescriptor()
==================================

The `handler.getOwnPropertyDescriptor()` method is a trap for [`Object.getOwnPropertyDescriptor()`](../../object/getownpropertydescriptor).

Syntax
------

    const p = new Proxy(target, {
      getOwnPropertyDescriptor: function(target, prop) {
      }
    });

### Parameters

The following parameters are passed to the `getOwnPropertyDescriptor()` method. `this` is bound to the handler.

`target`  
The target object.

`prop`  
The name of the property whose description should be retrieved.

### Return value

The `getOwnPropertyDescriptor()` method must return an object or `undefined`.

Description
-----------

The `handler.getOwnPropertyDescriptor()` method is a trap for [`Object.getOwnPropertyDescriptor()`](../../object/getownpropertydescriptor).

### Interceptions

This trap can intercept these operations:

-   [`Object.getOwnPropertyDescriptor()`](../../object/getownpropertydescriptor)
-   [`Reflect.getOwnPropertyDescriptor()`](../../reflect/getownpropertydescriptor)

### Invariants

If the following invariants are violated, the proxy will throw a [`TypeError`](../../typeerror):

-   `getOwnPropertyDescriptor()` must return an object or `undefined`.
-   A property cannot be reported as non-existent, if it exists as a non-configurable own property of the target object.
-   A property cannot be reported as non-existent, if it exists as an own property of the target object and the target object is not extensible.
-   A property cannot be reported as existent, if it does not exists as an own property of the target object and the target object is not extensible.
-   A property cannot be reported as non-configurable, if it does not exists as an own property of the target object or if it exists as a configurable own property of the target object.
-   The result of `Object.getOwnPropertyDescriptor(target)` can be applied to the target object using `Object.defineProperty()` and will not throw an exception.

Examples
--------

### Trapping of getOwnPropertyDescriptor

The following code traps [`Object.getOwnPropertyDescriptor()`](../../object/getownpropertydescriptor).

    const p = new Proxy({ a: 20}, {
      getOwnPropertyDescriptor: function(target, prop) {
        console.log('called: ' + prop);
        return { configurable: true, enumerable: true, value: 10 };
      }
    });

    console.log(Object.getOwnPropertyDescriptor(p, 'a').value); // "called: a"
                                                                // 10

The following code violates an invariant.

    const obj = { a: 10 };
    Object.preventExtensions(obj);
    const p = new Proxy(obj, {
      getOwnPropertyDescriptor: function(target, prop) {
        return undefined;
      }
    });

    Object.getOwnPropertyDescriptor(p, 'a'); // TypeError is thrown

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-proxy-object-internal-methods-and-internal-slots-getownproperty-p">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-proxy-object-internal-methods-and-internal-slots-getownproperty-p</span></a></td></tr></tbody></table>

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

18

No

36

10

49

49

18

36

10

5.0

See also
--------

-   [`Proxy`](../../proxy)
-   [`handler`](../proxy)
-   [`Object.getOwnPropertyDescriptor()`](../../object/getownpropertydescriptor)
-   [`Reflect.getOwnPropertyDescriptor()`](../../reflect/getownpropertydescriptor)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/getOwnPropertyDescriptor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/getOwnPropertyDescriptor</a>
