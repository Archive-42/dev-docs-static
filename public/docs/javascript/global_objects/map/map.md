Map() constructor
=================

The `Map()` creates [`Map`](../map) objects.

Syntax
------

    new Map()
    new Map(iterable)

### Parameters

 `iterable` <span class="badge inline optional">Optional</span>   
An [`Array`](../array) or other [iterable](../../iteration_protocols) object whose elements are key-value pairs. (For example, arrays with two elements, such as `[[ 1, 'one' ],[ 2, 'two' ]]`.) Each key-value pair is added to the new `Map`.

Examples
--------

### Creating a new Map

    let myMap = new Map([
      [1, 'one'],
      [2, 'two'],
      [3, 'three'],
    ])

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-map-constructor">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-map-constructor</span></a></td></tr></tbody></table>

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

`Map`

38

12

13

11

25

8

38

38

14

25

8

3.0

`iterable_allowed`

38

12

13

No

25

9

38

38

14

25

9

3.0

`new_required`

38

12

42

11

25

9

38

38

42

25

9

3.0

`null_allowed`

38

12

37

11

25

9

38

38

37

25

9

3.0

See also
--------

-   [`Set`](../set)
-   [`WeakMap`](../weakmap)
-   [`WeakSet`](../weakset)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/Map" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/Map</a>
