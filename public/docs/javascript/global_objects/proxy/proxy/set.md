handler.set()
=============

The `handler.set()` method is a trap for setting a property value.

Syntax
------

    const p = new Proxy(target, {
      set: function(target, property, value, receiver) {
      }
    });

### Parameters

The following parameters are passed to the `set()` method. `this` is bound to the handler.

`target`  
The target object.

`property`  
The name or [`Symbol`](../../symbol) of the property to set.

`value`  
The new value of the property to set.

`receiver`  
The object to which the assignment was originally directed. This is usually the proxy itself. But a `set()` handler can also be called indirectly, via the prototype chain or various other ways.

For example, suppose a script does `obj.name = "jen"`, and `obj` is not a proxy, and has no own property `.name`, but it has a proxy on its prototype chain. That proxy's `set()` handler will be called, and `obj` will be passed as the receiver.

### Return value

The `set()` method should return a boolean value.

-   Return `true` to indicate that assignment succeeded.
-   If the `set()` method returns `false`, and the assignment happened in strict-mode code, a [`TypeError`](../../typeerror) will be thrown.

Description
-----------

The `handler.set()` method is a trap for setting property value.

### Interceptions

This trap can intercept these operations:

-   Property assignment: `proxy[foo] = bar` and `proxy.foo = bar`
-   Inherited property assignment: `Object.create(proxy)[foo] = bar`
-   [`Reflect.set()`](../../reflect/set)

### Invariants

If the following invariants are violated, the proxy will throw a [`TypeError`](../../typeerror):

-   Cannot change the value of a property to be different from the value of the corresponding target object property if the corresponding target object property is a non-writable, non-configurable data property.
-   Cannot set the value of a property if the corresponding target object property is a non-configurable accessor property that has `undefined` as its `[[Set]]` attribute.
-   In strict mode, a `false` return value from the `set()` handler will throw a [`TypeError`](../../typeerror) exception.

Examples
--------

### Trap setting of a property value

The following code traps setting a property value.

    const p = new Proxy({}, {
      set: function(target, prop, value, receiver) {
        target[prop] = value;
        console.log('property set: ' + prop + ' = ' + value);
        return true;
      }
    })

    console.log('a' in p);  // false

    p.a = 10;               // "property set: a = 10"
    console.log('a' in p);  // true
    console.log(p.a);       // 10

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-proxy-object-internal-methods-and-internal-slots-set-p-v-receiver">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-proxy-object-internal-methods-and-internal-slots-set-p-v-receiver</span></a></td></tr></tbody></table>

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
-   [`Reflect.set()`](../../reflect/set)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/set" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/set</a>
