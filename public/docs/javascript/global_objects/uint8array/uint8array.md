Uint8Array() constructor
========================

The `Uint8Array()` constructor creates a typed array of 8-bit unsigned integers. The contents are initialized to `0`. Once established, you can reference elements in the array using the object's methods, or using standard array index syntax (that is, using bracket notation).

Syntax
------

    new Uint8Array(); // new in ES2017
    new Uint8Array(length);
    new Uint8Array(typedArray);
    new Uint8Array(object);

    new Uint8Array(buffer);
    new Uint8Array(buffer, byteOffset);
    new Uint8Array(buffer, byteOffset, length);

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

### Different ways to create a Uint8Array

    // From a length
    var uint8 = new Uint8Array(2);
    uint8[0] = 42;
    console.log(uint8[0]); // 42
    console.log(uint8.length); // 2
    console.log(uint8.BYTES_PER_ELEMENT); // 1

    // From an array
    var arr = new Uint8Array([21,31]);
    console.log(arr[1]); // 31

    // From another TypedArray
    var x = new Uint8Array([21, 31]);
    var y = new Uint8Array(x);
    console.log(y[0]); // 21

    // From an ArrayBuffer
    var buffer = new ArrayBuffer(8);
    var z = new Uint8Array(buffer, 1, 4);

    // From an iterable
    var iterable = function*(){ yield* [1,2,3]; }();
    var uint8 = new Uint8Array(iterable);
    // Uint8Array[1, 2, 3]

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-typedarray-constructors">ECMAScript (ECMA-262)<br />
<span class="small">The definition of 'TypedArray constructors' in that specification.</span></a></td></tr></tbody></table>

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

`Uint8Array`

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

???37

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

???37

18

44

14

5

1.0

### Compatibility notes

Starting with ECMAScript 2015, `Uint8Array` constructors require to be constructed with a [`new`](../../operators/new) operator. Calling a `Uint8Array` constructor as a function without `new`, will throw a [`TypeError`](../typeerror) from now on.

    var dv = Uint8Array([1, 2, 3]);
    // TypeError: calling a builtin Uint8Array constructor
    // without new is forbidden

    var dv = new Uint8Array([1, 2, 3]);

See also
--------

-   [JavaScript typed arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Typed_arrays)
-   [`ArrayBuffer`](../arraybuffer)
-   [`DataView`](../dataview)

?? 2005???2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint8Array/Uint8Array" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint8Array/Uint8Array</a>
