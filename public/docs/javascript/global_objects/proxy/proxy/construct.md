handler.construct()
===================

The `handler.construct()` method is a trap for the [`new`](../../../operators/new) operator. In order for the new operation to be valid on the resulting Proxy object, the target used to initialize the proxy must itself have a `[[Construct]]` internal method (i.e. `new target` must be valid).

Syntax
------

    const p = new Proxy(target, {
      construct: function(target, argumentsList, newTarget) {
      }
    });

### Parameters

The following parameters are passed to the `construct()` method. `this` is bound to the handler.

`target`  
The target object.

`argumentsList`  
The list of arguments for the constructor.

`newTarget`  
The constructor that was originally called, `p` above.

### Return value

The `construct` method must return an object.

Description
-----------

The `handler.construct()` method is a trap for the [`new`](../../../operators/new) operator.

### Interceptions

This trap can intercept these operations:

-   `new myFunction(...args)`
-   [`Reflect.construct()`](../../reflect/construct)

### Invariants

If the following invariants are violated, the proxy will throw a [`TypeError`](../../typeerror):

-   The result must be an `Object`.

Examples
--------

### Trapping the new operator

The following code traps the [`new`](../../../operators/new) operator.

    const p = new Proxy(function() {}, {
      construct: function(target, argumentsList, newTarget) {
        console.log('called: ' + argumentsList.join(', '));
        return { value: argumentsList[0] * 10 };
      }
    });

    console.log(new p(1).value); // "called: 1"
                                 // 10

The following code violates the invariant.

    const p = new Proxy(function() {}, {
      construct: function(target, argumentsList, newTarget) {
        return 1;
      }
    });

    new p(); // TypeError is thrown

The following code improperly initializes the proxy. The `target` in Proxy initialization must itself be a valid constructor for the [`new`](../../../operators/new) operator.

    const p = new Proxy({}, {
      construct: function(target, argumentsList, newTarget) {
        return {};
      }
    });

    new p(); // TypeError is thrown, "p" is not a constructor

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-proxy-object-internal-methods-and-internal-slots-construct-argumentslist-newtarget">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-proxy-object-internal-methods-and-internal-slots-construct-argumentslist-newtarget</span></a></td></tr></tbody></table>

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

`construct`

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
-   [`new`](../../../operators/new) operator.
-   [`Reflect.construct()`](../../reflect/construct)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/construct" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/construct</a>
