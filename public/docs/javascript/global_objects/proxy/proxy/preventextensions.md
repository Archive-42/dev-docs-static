handler.preventExtensions()
===========================

The `handler.preventExtensions()` method is a trap for [`Object.preventExtensions()`](../../object/preventextensions).

Syntax
------

    const p = new Proxy(target, {
      preventExtensions: function(target) {
      }
    });

### Parameters

The following parameter is passed to the `preventExtensions()` method. `this` is bound to the handler.

`target`  
The target object.

### Return value

The `preventExtensions()` method must return a boolean value.

Description
-----------

The `handler.preventExtensions()` method is a trap for [`Object.preventExtensions()`](../../object/preventextensions).

### Interceptions

This trap can intercept these operations:

-   [`Object.preventExtensions()`](../../object/preventextensions)
-   [`Reflect.preventExtensions()`](../../reflect/preventextensions)

### Invariants

If the following invariants are violated, the proxy will throw a [`TypeError`](../../typeerror):

-   `Object.preventExtensions(proxy)` only returns `true` if `Object.isExtensible(proxy)` is `false`.

Examples
--------

### Trapping of preventExtensions

The following code traps [`Object.preventExtensions()`](../../object/preventextensions).

    const p = new Proxy({}, {
      preventExtensions: function(target) {
        console.log('called');
        Object.preventExtensions(target);
        return true;
      }
    });

    console.log(Object.preventExtensions(p)); // "called"
                                              // false

The following code violates the invariant.

    const p = new Proxy({}, {
      preventExtensions: function(target) {
        return true;
      }
    });

    Object.preventExtensions(p); // TypeError is thrown

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-proxy-object-internal-methods-and-internal-slots-preventextensions">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-proxy-object-internal-methods-and-internal-slots-preventextensions</span></a></td></tr></tbody></table>

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

22

No

36

10

49

49

22

36

10

5.0

See also
--------

-   [`Proxy`](../../proxy)
-   [`handler`](../proxy)
-   [`Object.preventExtensions()`](../../object/preventextensions)
-   [`Reflect.preventExtensions()`](../../reflect/preventextensions)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/preventExtensions" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/preventExtensions</a>
