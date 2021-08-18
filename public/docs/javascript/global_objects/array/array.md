Array() constructor
===================

The `Array()` constructor is used to create [`Array`](../array) objects.

Syntax
------

    // literal constructor
    [element0, element1, ..., elementN]

    // construct from elements
    new Array(element0, element1, ..., elementN)

    // construct from array length
    new Array(arrayLength)

### Parameters

`elementN`  
A JavaScript array is initialized with the given elements, except in the case where a single argument is passed to the `Array` constructor and that argument is a number (see the arrayLength parameter below). Note that this special case only applies to JavaScript arrays created with the `Array` constructor, not array literals created with the bracket syntax.

`arrayLength`  
If the only argument passed to the `Array` constructor is an integer between 0 and 2<sup>32</sup>-1 (inclusive), this returns a new JavaScript array with its `length` property set to that number (**Note:** this implies an array of `arrayLength` empty slots, not slots with actual `undefined` values). If the argument is any other number, a [`RangeError`](../rangeerror) exception is thrown.

Examples
--------

### Array literal notation

Arrays can be created using the [literal](../../lexical_grammar#array_literals) notation:

    let fruits = ['Apple', 'Banana'];

    console.log(fruits.length); // 2
    console.log(fruits[0]);     // "Apple"

### Array constructor with a single parameter

Arrays can be created using a constructor with a single number parameter. An array with its `length` property set to that number and the array elements are empty slots.

    let fruits = new Array(2);

    console.log(fruits.length); // 2
    console.log(fruits[0]);     // undefined

### Array constructor with multiple parameters

If more than one argument is passed to the constructor, a new [`Array`](../array) with the given elements is created.

    let fruits = new Array('Apple', 'Banana');

    console.log(fruits.length); // 2
    console.log(fruits[0]);     // "Apple"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-array-constructor">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-array-constructor</span></a></td></tr></tbody></table>

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

`Array`

1

12

1

4

4

1

≤37

18

4

10.1

1

1.0

See also
--------

-   [`Array`](../array) class

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Array" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Array</a>
