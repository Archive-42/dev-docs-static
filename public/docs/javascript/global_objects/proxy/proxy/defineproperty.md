handler.defineProperty()
========================

The `handler.defineProperty()` method is a trap for [`Object.defineProperty()`](../../object/defineproperty).

Syntax
------

    const p = new Proxy(target, {
      defineProperty: function(target, property, descriptor) {
      }
    });

### Parameters

The following parameters are passed to the `defineProperty()` method. `this` is bound to the handler.

`target`  
The target object.

`property`  
The name or [`Symbol`](../../symbol) of the property whose description is to be retrieved.

`descriptor`  
The descriptor for the property being defined or modified.

### Return value

The `defineProperty()` method must return a [`Boolean`](../../boolean) indicating whether or not the property has been successfully defined.

Description
-----------

The `handler.defineProperty()` method is a trap for [`Object.defineProperty()`](../../object/defineproperty).

### Interceptions

This trap can intercept these operations:

-   [`Object.defineProperty()`](../../object/defineproperty)
-   [`Reflect.defineProperty()`](../../reflect/defineproperty)

### Invariants

If the following invariants are violated, the proxy will throw a [`TypeError`](../../typeerror):

-   A property cannot be added, if the target object is not extensible.
-   A property cannot be added as or modified to be non-configurable, if it does not exists as a non-configurable own property of the target object.
-   A property may not be non-configurable, if a corresponding configurable property of the target object exists.
-   If a property has a corresponding target object property then `Object.defineProperty(target, prop, descriptor)` will not throw an exception.
-   In strict mode, a `false` return value from the `defineProperty()` handler will throw a [`TypeError`](../../typeerror) exception.

Examples
--------

### Trapping of defineProperty

The following code traps [`Object.defineProperty()`](../../object/defineproperty).

    const p = new Proxy({}, {
      defineProperty: function(target, prop, descriptor) {
        console.log('called: ' + prop);
        return true;
      }
    });

    const desc = { configurable: true, enumerable: true, value: 10 };
    Object.defineProperty(p, 'a', desc); // "called: a"

When calling [`Object.defineProperty()`](../../object/defineproperty) or [`Reflect.defineProperty()`](../../reflect/defineproperty), the `descriptor` passed to `defineProperty()` trap has one restriction—only following properties are usable (non-standard properties will be ignored):

-   `enumerable`
-   `configurable`
-   `writable`
-   `value`
-   `get`
-   `set`

<!-- -->

    const p = new Proxy({}, {
      defineProperty(target, prop, descriptor) {
        console.log(descriptor);
        return Reflect.defineProperty(target, prop, descriptor);
      }
    });

    Object.defineProperty(p, 'name', {
      value: 'proxy',
      type: 'custom'
    });  // { value: 'proxy' }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-proxy-object-internal-methods-and-internal-slots-defineownproperty-p-desc">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-proxy-object-internal-methods-and-internal-slots-defineownproperty-p-desc</span></a></td></tr></tbody></table>

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
-   [`Object.defineProperty()`](../../object/defineproperty)
-   [`Reflect.defineProperty()`](../../reflect/defineproperty)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/defineProperty" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/defineProperty</a>
