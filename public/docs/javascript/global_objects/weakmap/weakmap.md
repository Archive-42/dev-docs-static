WeakMap() constructor
=====================

The `WeakMap()` creates `WeakMap` objects which are a collections of key/value pairs in which the keys are weakly referenced. The keys must be objects and the values can be arbitrary values.

You can learn more about `WeakMap`s in the section [WeakMap object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Keyed_collections#weakmap_object) in [Keyed collections](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Keyed_collections).

Syntax
------

    new WeakMap()
    new WeakMap(iterable)

### Parameters

`iterable`  
Iterable is an Array or other iterable object whose elements are key-value pairs (2-element Arrays). Each key-value pair will be added to the new WeakMap. null is treated as undefined.

Examples
--------

### Using WeakMap

    const wm1 = new WeakMap(),
          wm2 = new WeakMap(),
          wm3 = new WeakMap();
    const o1 = {},
          o2 = function() {},
          o3 = window;

    wm1.set(o1, 37);
    wm1.set(o2, 'azerty');
    wm2.set(o1, o2); // a value can be anything, including an object or a function
    wm2.set(o3, undefined);
    wm2.set(wm1, wm2); // keys and values can be any objects. Even WeakMaps!

    wm1.get(o2); // "azerty"
    wm2.get(o2); // undefined, because there is no key for o2 on wm2
    wm2.get(o3); // undefined, because that is the set value

    wm1.has(o2); // true
    wm2.has(o2); // false
    wm2.has(o3); // true (even if the value itself is 'undefined')

    wm3.set(o1, 37);
    wm3.get(o1); // 37

    wm1.has(o1); // true
    wm1.delete(o1);
    wm1.has(o1); // false

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-weakmap-constructor">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-weakmap-constructor</span></a></td></tr></tbody></table>

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

`WeakMap`

36

12

6

11

23

8

37

36

6

24

8

3.0

`iterable_allowed`

38

12

36

No

25

9

38

38

36

25

9

3.0

`new_required`

36

12

42

11

23

9

37

36

42

24

9

3.0

`null_allowed`

36

12

37

11

23

8

37

36

37

24

8

3.0

See also
--------

-   [`WeakMap` in the JavaScript guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Keyed_collections#weakmap_object)
-   [Hiding Implementation Details with ECMAScript 6 WeakMaps](https://fitzgeraldnick.com/weblog/53/)
-   [`Map`](../map)
-   [`Set`](../set)
-   [`WeakSet`](../weakset)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakMap/WeakMap" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakMap/WeakMap</a>
