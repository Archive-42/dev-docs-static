Set.prototype.forEach()
=======================

The `forEach()` method executes a provided function once for each value in the `Set` object, in insertion order.

Syntax
------

    // Arrow function
    forEach(() => { ... } )
    forEach((value) => { ... } )
    forEach((value, key) => { ... } )
    forEach((value, key, set) => { ... } )

    // Callback function
    forEach(callbackFn)
    forEach(callbackFn, thisArg)

    // Inline callback function
    forEach(function callbackFn() { ... })
    forEach(function callbackFn(value) { ... })
    forEach(function callbackFn(value, key) { ... })
    forEach(function callbackFn(value, key, set) { ... })
    forEach(function callbackFn(value, key, set) { ... }, thisArg)

### Parameters

`callback`  
Function to execute for each element, taking three arguments:

 `value`, `key`   
The current element being processed in the `Set`. As there are no keys in `Set`, the value is passed for both arguments.

`set`  
The `Set` object which `forEach()` was called upon.

`thisArg`  
Value to use as `this` when executing `callbackFn`.

### Return value

[`undefined`](../undefined).

Description
-----------

The `forEach()` method executes the provided `callback` once for each value which actually exists in the `Set` object. It is not invoked for values which have been deleted. However, it is executed for values which are present but have the value `undefined`.

`callback` is invoked with **three arguments**:

-   the **element value**
-   the **element key**
-   the `Set`

There are no keys in `Set` objects, however, so the first two arguments are both **values** contained in the [`Set`](../set). This is to make it consistent with other `forEach()` methods for [`Map`](../map/foreach) and [`Array`](../array/foreach).

If a `thisArg` parameter is provided to `forEach()`, it will be passed to `callback` when invoked, for use as its `this` value. Otherwise, the value `undefined` will be passed for use as its `this` value. The `this` value ultimately observable by `callback` is determined according to [the usual rules for determining the `this` seen by a function](../../operators/this).

Each value is visited once, except in the case when it was deleted and re-added before `forEach()` has finished. `callback` is not invoked for values deleted before being visited. New values added before `forEach()` has finished will be visited.

`forEach()` executes the `callback` function once for each element in the `Set` object; it does not return a value.

Examples
--------

### Logging the contents of a Set object

The following code logs a line for each element in a `Set` object:

    function logSetElements(value1, value2, set) {
        console.log('s[' + value1 + '] = ' + value2);
    }

    new Set(['foo', 'bar', undefined]).forEach(logSetElements);

    // logs:
    // "s[foo] = foo"
    // "s[bar] = bar"
    // "s[undefined] = undefined"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-set.prototype.foreach">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-set.prototype.foreach</span></a></td></tr></tbody></table>

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

`forEach`

38

12

25

11

25

8

38

38

25

25

8

3.0

See also
--------

-   [`Array.prototype.forEach()`](../array/foreach)
-   [`Map.prototype.forEach()`](../map/foreach)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/forEach" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/forEach</a>
