handler.setPrototypeOf()
========================

The `handler.setPrototypeOf()` method is a trap for [`Object.setPrototypeOf()`](../../object/setprototypeof).

Syntax
------

    const p = new Proxy(target, {
      setPrototypeOf: function(target, prototype) {
      }
    });

### Parameters

The following parameters are passed to the `setPrototypeOf()` method. `this` is bound to the handler.

`target`  
The target object.

`prototype`  
The object's new prototype or `null`.

### Return value

The `setPrototypeOf()` method returns `true` if the `[[Prototype]]` was successfully changed, otherwise `false`.

Description
-----------

The `handler.setPrototypeOf()` method is a trap for [`Object.setPrototypeOf()`](../../object/setprototypeof).

### Interceptions

This trap can intercept these operations:

-   [`Object.setPrototypeOf()`](../../object/setprototypeof)
-   [`Reflect.setPrototypeOf()`](../../reflect/setprototypeof)

### Invariants

If the following invariants are violated, the proxy will throw a [`TypeError`](../../typeerror):

-   If `target` is not extensible, the `prototype` parameter must be the same value as `Object.getPrototypeOf(target)`.

Examples
--------

If you want to disallow setting a new prototype for your object, your handler's `setPrototypeOf()` method can either return `false`, or it can throw an exception.

### Approach 1: Returning false

This approach means that any mutating operation that throws an exception on failure to mutate, must create the exception itself.

For example, [`Object.setPrototypeOf()`](../../object/setprototypeof) will create and throw a [`TypeError`](../../typeerror) itself. If the mutation is performed by an operation that *doesn't* ordinarily throw in case of failure, such as [`Reflect.setPrototypeOf()`](../../reflect/setprototypeof), no exception will be thrown.

    const handlerReturnsFalse = {
        setPrototypeOf(target, newProto) {
            return false;
        }
    };

    const newProto = {}, target = {};

    const p1 = new Proxy(target, handlerReturnsFalse);
    Object.setPrototypeOf(p1, newProto); // throws a TypeError
    Reflect.setPrototypeOf(p1, newProto); // returns false

### Approach 2: Throwing an Exception

The latter approach will cause *any* operation that attempts to mutate, to throw. This approach is best if you want even non-throwing operations to throw on failure, or you want to throw a custom exception value.

    const handlerThrows = {
        setPrototypeOf(target, newProto) {
            throw new Error('custom error');
        }
    };

    const newProto = {}, target = {};

    const p2 = new Proxy(target, handlerThrows);
    Object.setPrototypeOf(p2, newProto);  // throws new Error("custom error")
    Reflect.setPrototypeOf(p2, newProto); // throws new Error("custom error")

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-proxy-object-internal-methods-and-internal-slots-setprototypeof-v">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-proxy-object-internal-methods-and-internal-slots-setprototypeof-v</span></a></td></tr></tbody></table>

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

`setPrototypeOf`

49

12

49

No

36

10

49

49

49

36

10

5.0

See also
--------

-   [`Proxy`](../../proxy)
-   [`handler`](../proxy)
-   [`Object.setPrototypeOf()`](../../object/setprototypeof)
-   [`Reflect.setPrototypeOf()`](../../reflect/setprototypeof)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/setPrototypeOf" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/setPrototypeOf</a>
