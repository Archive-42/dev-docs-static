Array.prototype.keys()
======================

The `keys()` method returns a new **Array Iterator** object that contains the keys for each index in the array.

Syntax
------

    keys()

### Return value

A new [`Array`](../array) iterator object.

Examples
--------

### Key iterator doesn't ignore holes

    var arr = ['a', , 'c'];
    var sparseKeys = Object.keys(arr);
    var denseKeys = [...arr.keys()];
    console.log(sparseKeys); // ['0', '2']
    console.log(denseKeys);  // [0, 1, 2]

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-array.prototype.keys">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-array.prototype.keys</span></a></td></tr></tbody></table>

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

`keys`

38

12

28

No

25

8

38

38

28

25

8

3.0

See also
--------

-   [`Array.prototype.values()`](values)
-   [`Array.prototype.entries()`](entries)
-   [Iteration protocols](../../iteration_protocols)
-   [A polyfill](https://github.com/behnammodi/polyfill/blob/master/array.polyfill.js)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/keys" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/keys</a>
