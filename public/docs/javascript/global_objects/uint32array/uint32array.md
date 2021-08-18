Uint32Array() constructor
=========================

The `Uint32Array()` typed array constructor creates an array of 32-bit unsigned integers in the platform byte order. If control over byte order is needed, use [`DataView`](../dataview) instead. The contents are initialized to `0`. Once established, you can reference elements in the array using the object's methods, or using standard array index syntax (that is, using bracket notation).

Syntax
------

    new Uint32Array(); // new in ES2017
    new Uint32Array(length);
    new Uint32Array(typedArray);
    new Uint32Array(object);

    new Uint32Array(buffer);
    new Uint32Array(buffer, byteOffset);
    new Uint32Array(buffer, byteOffset, length);

### Parameters

`length`  
When called with a `length` argument, an internal array buffer is created in memory, of size `length` *multiplied by `BYTES_PER_ELEMENT`* bytes, containing zeros.

`typedArray`  
When called with a `typedArray` argument, which can be an object of any of the typed array types (such as `Int32Array`), the `typedArray` gets copied into a new typed array. Each value in `typedArray` is converted to the corresponding type of the constructor before being copied into the new array. The length of the new typed array will be same as the length of the `typedArray` argument.

`object`  
When called with an `object` argument, a new typed array is created as if by the `TypedArray.from()` method.

 `buffer`, `byteOffset`, `length`   
When called with a `buffer`, and optionally a `byteOffset` and a `length` argument, a new typed array view is created that views the specified [`ArrayBuffer`](../arraybuffer). The `byteOffset` and `length` parameters specify the memory range that will be exposed by the typed array view. If both are omitted, all of `buffer` is viewed; if only `length` is omitted, the remainder of `buffer` is viewed.

Examples
--------

### Different ways to create a Uint32Array

    // From a length
    var uint32 = new Uint32Array(2);
    uint32[0] = 42;
    console.log(uint32[0]); // 42
    console.log(uint32.length); // 2
    console.log(uint32.BYTES_PER_ELEMENT); // 4

    // From an array
    var arr = new Uint32Array([21,31]);
    console.log(arr[1]); // 31

    // From another TypedArray
    var x = new Uint32Array([21, 31]);
    var y = new Uint32Array(x);
    console.log(y[0]); // 21

    // From an ArrayBuffer
    var buffer = new ArrayBuffer(16);
    var z = new Uint32Array(buffer, 0, 4);

    // From an iterable
    var iterable = function*(){ yield* [1,2,3]; }();
    var uint32 = new Uint32Array(iterable);
    // Uint32Array[1, 2, 3]

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-typedarray-constructors">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-typedarray-constructors</span></a></td></tr></tbody></table>

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

`Uint32Array`

7

12

4

10

11.6

5.1

4

18

4

12

4.2

1.0

`constructor_without_arguments`

7

12

55

10

11.6

5.1

≤37

18

55

12

5

1.0

`iterable_allowed`

39

14

52

No

26

10

39

39

52

26

10

4.0

`new_required`

7

14

44

No

15

5.1

≤37

18

44

14

5

1.0

### Compatibility notes

Starting with ECMAScript 2015, `Uint32Array` constructors require to be constructed with a [`new`](../../operators/new) operator. Calling a `Uint32Array` constructor as a function without `new`, will throw a [`TypeError`](../typeerror) from now on.

    var dv = Uint32Array([1, 2, 3]);
    // TypeError: calling a builtin Uint32Array constructor
    // without new is forbidden

    var dv = new Uint32Array([1, 2, 3]);

See also
--------

-   [JavaScript typed arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Typed_arrays)
-   [`ArrayBuffer`](../arraybuffer)
-   [`DataView`](../dataview)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint32Array/Uint32Array" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint32Array/Uint32Array</a>
