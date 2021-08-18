Map.prototype.forEach()
=======================

The `forEach()` method executes a provided function once per each key/value pair in the `Map` object, in insertion order.

Syntax
------

    // Arrow function
    forEach(() => { ... } )
    forEach((value) => { ... } )
    forEach((value, key) => { ... } )
    forEach((value, key, map) => { ... } )

    // Callback function
    forEach(callbackFn)
    forEach(callbackFn, thisArg)

    // Inline callback function
    forEach(function callbackFn() { ... })
    forEach(function callbackFn(value) { ... })
    forEach(function callbackFn(value, key) { ... })
    forEach(function callbackFn(value, key, map) { ... })
    forEach(function callbackFn(value, key, map) { ... }, thisArg)

### Parameters

`callbackFn`  
Function to execute for each entry of `myMap`. It takes the following arguments:

 `value` <span class="badge inline optional">Optional</span>   
Value of each iteration.

 `key` <span class="badge inline optional">Optional</span>   
Key of each iteration.

 `map` <span class="badge inline optional">Optional</span>   
The map being iterated (`myMap` in the above Syntax box).

 `thisArg` <span class="badge inline optional">Optional</span>   
Value to use as `this` when executing `callback`.

### Return value

[`undefined`](../undefined).

Description
-----------

The `forEach` method executes the provided `callback` once for each key of the map which actually exist. It is not invoked for keys which have been deleted. However, it is executed for values which are present but have the value `undefined`.

`callback` is invoked with **three arguments**:

-   the entry's `value`
-   the entry's `key`
-   the `Map` being traversed

If a `thisArg` parameter is provided to `forEach`, it will be passed to `callback` when invoked, for use as its `this` value. Otherwise, the value `undefined` will be passed for use as its `this` value. The `this` value ultimately observable by `callback` is determined according to [the usual rules for determining the `this` seen by a function](../../operators/this).

Each value is visited once, except in the case when it was deleted and re-added before `forEach` has finished. `callback` is not invoked for values deleted before being visited. New values added before `forEach` has finished will be visited.

Examples
--------

### Printing the contents of a Map object

The following code logs a line for each element in an `Map` object:

    function logMapElements(value, key, map) {
        console.log(`map.get('${key}') = ${value}`)
    }
    new Map([['foo', 3], ['bar', {}], ['baz', undefined]]).forEach(logMapElements)
    // logs:
    // "map.get('foo') = 3"
    // "map.get('bar') = [object Object]"
    // "map.get('baz') = undefined"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-map.prototype.foreach">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-map.prototype.foreach</span></a></td></tr></tbody></table>

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
-   [`Set.prototype.forEach()`](../set/foreach)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/forEach" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/forEach</a>
