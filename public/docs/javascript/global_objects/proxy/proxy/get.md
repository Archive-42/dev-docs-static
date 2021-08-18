handler.get()
=============

The `handler.get()` method is a trap for getting a property value.

Syntax
------

    const p = new Proxy(target, {
      get: function(target, property, receiver) {
      }
    });

### Parameters

The following parameters are passed to the `get()` method. `this` is bound to the handler.

`target`  
The target object.

`property`  
The name or [`Symbol`](../../symbol) of the property to get.

`receiver`  
Either the proxy or an object that inherits from the proxy.

### Return value

The `get()` method can return any value.

Description
-----------

The `handler.get()` method is a trap for getting a property value.

### Interceptions

This trap can intercept these operations:

-   Property access: `proxy[foo]`and `proxy.bar`
-   Inherited property access: `Object.create(proxy)[foo]`
-   [`Reflect.get()`](../../reflect/get)

### Invariants

If the following invariants are violated, the proxy will throw a [`TypeError`](../../typeerror):

-   The value reported for a property must be the same as the value of the corresponding target object property if the target object property is a non-writable, non-configurable own data property.
-   The value reported for a property must be undefined if the corresponding target object property is a non-configurable own accessor property that has `undefined` as its `[[Get]]` attribute.

Examples
--------

### Trap for getting a property value

The following code traps getting a property value.

    const p = new Proxy({}, {
      get: function(target, property, receiver) {
        console.log('called: ' + property);
        return 10;
      }
    });

    console.log(p.a); // "called: a"
                      // 10

The following code violates an invariant.

    const obj = {};
    Object.defineProperty(obj, 'a', {
      configurable: false,
      enumerable: false,
      value: 10,
      writable: false
    });

    const p = new Proxy(obj, {
      get: function(target, property) {
        return 20;
      }
    });

    p.a; // TypeError is thrown

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-proxy-object-internal-methods-and-internal-slots-get-p-receiver">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-proxy-object-internal-methods-and-internal-slots-get-p-receiver</span></a></td></tr></tbody></table>

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
-   [`Reflect.get()`](../../reflect/get)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/get" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/get</a>
