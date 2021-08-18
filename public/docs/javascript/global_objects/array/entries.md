Array.prototype.entries()
=========================

The `entries()` method returns a new **Array Iterator** object that contains the key/value pairs for each index in the array.

Syntax
------

    entries()

### Return value

A new [`Array`](../array) iterator object.

Examples
--------

### Iterating with index and element

    const a = ['a', 'b', 'c'];

    for (const [index, element] of a.entries())
      console.log(index, element);

    // 0 'a'
    // 1 'b'
    // 2 'c'

### Using a for…of loop

    var a = ['a', 'b', 'c'];
    var iterator = a.entries();

    for (let e of iterator) {
      console.log(e);
    }
    // [0, 'a']
    // [1, 'b']
    // [2, 'c']

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-array.prototype.entries">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-array.prototype.entries</span></a></td></tr></tbody></table>

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

`entries`

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

-   [`Array.prototype.keys()`](keys)
-   [`Array.prototype.values()`](values)
-   [`Array.prototype.forEach()`](foreach)
-   [`Array.prototype.every()`](every)
-   [`Array.prototype.some()`](some)
-   [for...of](../../statements/for...of)
-   [Iteration protocols](../../iteration_protocols)
-   [A polyfill](https://github.com/behnammodi/polyfill/blob/master/array.polyfill.js)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/entries" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/entries</a>
