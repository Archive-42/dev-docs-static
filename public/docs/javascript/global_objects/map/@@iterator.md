Map.prototype\[@@iterator\]()
=============================

The initial value of the `@@iterator` property is the same function object as the initial value of the [`entries`](entries) method.

Syntax
------

    myMap[Symbol.iterator]

### Return value

The map **iterator** function, which is the [`entries()`](entries) function by default.

Examples
--------

### Using \[@@iterator\]()

    const myMap = new Map()
    myMap.set('0', 'foo')
    myMap.set(1, 'bar')
    myMap.set({}, 'baz')

    const mapIter = myMap[Symbol.iterator]()

    console.log(mapIter.next().value) // ["0", "foo"]
    console.log(mapIter.next().value) // [1, "bar"]
    console.log(mapIter.next().value) // [Object, "baz"]

### Using \[@@iterator\]() with for..of

    const myMap = new Map()
    myMap.set('0', 'foo')
    myMap.set(1, 'bar')
    myMap.set({}, 'baz')

    for (const entry of myMap) {
      console.log(entry)
    }
    // ["0", "foo"]
    // [1, "bar"]
    // [{}, "baz"]

    for (const [key, value] of myMap) {
      console.log(`${key}: ${value}`)
    }
    // 0: foo
    // 1: bar
    // [Object]: baz

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-map.prototype-@@iterator">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-map.prototype-@@iterator</span></a></td></tr></tbody></table>

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

`@@iterator`

43

12

36

27-36

A placeholder property named `@@iterator` is used.

17-27

A placeholder property named `iterator` is used.

No

30

10

43

43

36

27-36

A placeholder property named `@@iterator` is used.

17-27

A placeholder property named `iterator` is used.

30

10

4.0

See also
--------

-   [`Map.prototype.entries()`](entries)
-   [`Map.prototype.keys()`](keys)
-   [`Map.prototype.values()`](values)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/@@iterator" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/@@iterator</a>
