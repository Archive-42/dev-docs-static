WeakSet() constructor
=====================

The `WeakSet` constructor lets you create `WeakSet` objects that store weakly held *objects* in a collection.

Syntax
------

    new WeakSet()
    new WeakSet(iterable)

### Parameters

iterable  
If an [iterable object](../../statements/for...of) is passed, all of its elements will be added to the new `WeakSet`. null is treated as undefined.

Examples
--------

### Using the WeakSet object

    var ws = new WeakSet();
    var foo = {};
    var bar = {};

    ws.add(foo);
    ws.add(bar);

    ws.has(foo);    // true
    ws.has(bar);    // true

    ws.delete(foo); // removes foo from the set
    ws.has(foo);    // false, foo has been removed
    ws.has(bar);    // true, bar is retained

Note that `foo !== bar`. While they are similar objects, *they are not **the same object***. And so they are both added to the set.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-weakset-constructor">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-weakset-constructor</span></a></td></tr></tbody></table>

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

`WeakSet`

36

12

34

No

23

9

37

36

34

24

9

3.0

`iterable_allowed`

38

12

34

No

25

9

38

38

34

25

9

3.0

`null_allowed`

36

12

37

No

23

9

37

36

37

24

9

3.0

See also
--------

-   [`WeakSet`](../weakset)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakSet/WeakSet" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakSet/WeakSet</a>
