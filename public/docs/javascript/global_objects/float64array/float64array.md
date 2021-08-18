Float64Array() constructor
==========================

The `Float64Array()` typed array constructor creates a new [`Float64Array`](../float64array) object, which is, an array of 64-bit floating point numbers (corresponding to the C `double` data type) in the platform byte order. If control over byte order is needed, use [`DataView`](../dataview) instead. The contents are initialized to `0`. Once established, you can reference elements in the array using the object's methods, or using standard array index syntax (that is, using bracket notation).

Syntax
------

    new Float64Array(); // new in ES2017
    new Float64Array(length);
    new Float64Array(typedArray);
    new Float64Array(object);

    new Float64Array(buffer);
    new Float64Array(buffer, byteOffset);
    new Float64Array(buffer, byteOffset, length);

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

### Different ways to create a Float64Array

    // From a length
    var float64 = new Float64Array(2);
    float64[0] = 42;
    console.log(float64[0]); // 42
    console.log(float64.length); // 2
    console.log(float64.BYTES_PER_ELEMENT); // 8

    // From an array
    var arr = new Float64Array([21,31]);
    console.log(arr[1]); // 31

    // From another TypedArray
    var x = new Float64Array([21, 31]);
    var y = new Float64Array(x);
    console.log(y[0]); // 21

    // From an ArrayBuffer
    var buffer = new ArrayBuffer(32);
    var z = new Float64Array(buffer, 0, 4);

    // From an iterable
    var iterable = function*(){ yield* [1,2,3]; }();
    var float64 = new Float64Array(iterable);
    // Float64Array[1, 2, 3]

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

`Float64Array`

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

Starting with ECMAScript 2015, `Float64Array` constructors require to be constructed with a [`new`](../../operators/new) operator. Calling a `Float64Array` constructor as a function without `new`, will throw a [`TypeError`](../typeerror) from now on.

    var dv = Float64Array([1, 2, 3]);
    // TypeError: calling a builtin Float64Array constructor
    // without new is forbidden

    var dv = new Float64Array([1, 2, 3]);

See also
--------

-   [JavaScript typed arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Typed_arrays)
-   [`ArrayBuffer`](../arraybuffer)
-   [`DataView`](../dataview)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float64Array/Float64Array" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float64Array/Float64Array</a>
