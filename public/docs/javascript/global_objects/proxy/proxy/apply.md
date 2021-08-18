handler.apply()
===============

The `handler.apply()` method is a trap for a function call.

Syntax
------

    const p = new Proxy(target, {
      apply: function(target, thisArg, argumentsList) {
      }
    });

### Parameters

The following parameters are passed to the `apply()` method. `this` is bound to the handler.

`target`  
The target object.

`thisArg`  
The `this` argument for the call.

`argumentsList`  
The list of arguments for the call.

### Return value

The `apply()` method can return any value.

Description
-----------

The `handler.apply()` method is a trap for a function call.

### Interceptions

This trap can intercept these operations:

-   `proxy(...args)`
-   [`Function.prototype.apply()`](../../function/apply) and [`Function.prototype.call()`](../../function/call)
-   [`Reflect.apply()`](../../reflect/apply)

### Invariants

If the following invariants are violated, the proxy will throw a [`TypeError`](../../typeerror).

The `target` must be a callable itself. That is, it must be a function object.

Examples
--------

### Trapping a function call

The following code traps a function call.

    const p = new Proxy(function() {}, {
      apply: function(target, thisArg, argumentsList) {
        console.log('called: ' + argumentsList.join(', '));
        return argumentsList[0] + argumentsList[1] + argumentsList[2];
      }
    });

    console.log(p(1, 2, 3)); // "called: 1, 2, 3"
                             // 6

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-proxy-object-internal-methods-and-internal-slots-call-thisargument-argumentslist">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-proxy-object-internal-methods-and-internal-slots-call-thisargument-argumentslist</span></a></td></tr></tbody></table>

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

`apply`

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
-   [`Function.prototype.apply()`](../../function/apply)
-   [`Function.prototype.call()`](../../function/call)
-   [`Reflect.apply()`](../../reflect/apply)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/apply" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/apply</a>
