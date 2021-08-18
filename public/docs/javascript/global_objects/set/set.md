Set() constructor
=================

The `Set` lets you create `Set` objects that store unique values of any type, whether [primitive values](https://developer.mozilla.org/en-US/docs/Glossary/Primitive) or object references.

Syntax
------

    new Set()
    new Set(iterable)

### Parameters

 `iterable` <span class="badge inline optional">Optional</span>   
If an [iterable object](../../statements/for...of) is passed, all of its elements will be added to the new `Set`.

If you don't specify this parameter, or its value is `null`, the new `Set` is empty.

### Return value

A new `Set` object.

Examples
--------

### Using the `Set` object

    let mySet = new Set()

    mySet.add(1)           // Set [ 1 ]
    mySet.add(5)           // Set [ 1, 5 ]
    mySet.add(5)           // Set [ 1, 5 ]
    mySet.add('some text') // Set [ 1, 5, 'some text' ]
    let o = {a: 1, b: 2}
    mySet.add(o)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-set-constructor">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-set-constructor</span></a></td></tr></tbody></table>

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

`Set`

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

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/Set" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/Set</a>
