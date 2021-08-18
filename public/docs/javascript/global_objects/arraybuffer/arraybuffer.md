ArrayBuffer() constructor
=========================

The `ArrayBuffer()` constructor is used to create [`ArrayBuffer`](../arraybuffer) objects.

Syntax
------

    new ArrayBuffer(length)

### Parameters

`length`  
The size, in bytes, of the array buffer to create.

### Return value

A new `ArrayBuffer` object of the specified size. Its contents are initialized to 0.

### Exceptions

A [`RangeError`](../rangeerror) is thrown if the `length` is larger than [`Number.MAX_SAFE_INTEGER`](../number/max_safe_integer) (&gt;= 2 \*\* 53) or negative.

Compatibility notes
-------------------

Starting with ECMAScript 2015, `ArrayBuffer` constructors require to be constructed with a [`new`](../../operators/new) operator. Calling an `ArrayBuffer` constructor as a function without `new`, will throw a [`TypeError`](../typeerror) from now on.

    var dv = ArrayBuffer(10);
    // TypeError: calling a builtin ArrayBuffer constructor
    // without new is forbidden

    var dv = new ArrayBuffer(10);

Examples
--------

### Creating an ArrayBuffer

In this example, we create a 8-byte buffer with a [`Int32Array`](../int32array) view referring to the buffer:

    var buffer = new ArrayBuffer(8);
    var view   = new Int32Array(buffer);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-arraybuffer-constructor">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-arraybuffer-constructor</span></a></td></tr></tbody></table>

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

`ArrayBuffer`

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

See also
--------

-   [JavaScript typed arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Typed_arrays)
-   [`SharedArrayBuffer`](../sharedarraybuffer)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer/ArrayBuffer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer/ArrayBuffer</a>
