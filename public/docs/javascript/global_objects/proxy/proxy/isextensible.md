handler.isExtensible()
======================

The `handler.isExtensible()` method is a trap for [`Object.isExtensible()`](../../object/isextensible).

Syntax
------

    const p = new Proxy(target, {
      isExtensible: function(target) {
      }
    });

### Parameters

The following parameter is passed to the `isExtensible()` method. `this` is bound to the handler.

`target`  
The target object.

### Return value

The `isExtensible()` method must return a boolean value.

Description
-----------

The `handler.isExtensible()` method is a trap for [`Object.isExtensible()`](../../object/isextensible).

### Interceptions

This trap can intercept these operations:

-   [`Object.isExtensible()`](../../object/isextensible)
-   [`Reflect.isExtensible()`](../../reflect/isextensible)

### Invariants

If the following invariants are violated, the proxy will throw a [`TypeError`](../../typeerror):

-   `Object.isExtensible(proxy)` must return the same value as `Object.isExtensible(target)`.

Examples
--------

### Trapping of isExtensible

The following code traps [`Object.isExtensible()`](../../object/isextensible).

    const p = new Proxy({}, {
      isExtensible: function(target) {
        console.log('called');
        return true;
      }
    });

    console.log(Object.isExtensible(p)); // "called"
                                         // true

The following code violates the invariant.

    const p = new Proxy({}, {
      isExtensible: function(target) {
        return false;
      }
    });

    Object.isExtensible(p); // TypeError is thrown

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-proxy-object-internal-methods-and-internal-slots-isextensible">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-proxy-object-internal-methods-and-internal-slots-isextensible</span></a></td></tr></tbody></table>

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

`isExtensible`

49

12

31

No

36

10

49

49

31

36

10

5.0

See also
--------

-   [`Proxy`](../../proxy)
-   [`handler`](../proxy)
-   [`Object.isExtensible()`](../../object/isextensible)
-   [`Reflect.isExtensible()`](../../reflect/isextensible)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/isExtensible" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/isExtensible</a>
