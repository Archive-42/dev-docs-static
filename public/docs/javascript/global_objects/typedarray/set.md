TypedArray.prototype.set()
==========================

The `set()` method stores multiple values in the typed array, reading input values from a specified array.

Syntax
------

    set(array)
    set(array, offset)

    set(typedarray)
    set(typedarray, offset)

### Parameters

`array`  
The array from which to copy values. All values from the source array are copied into the target array, unless the length of the source array plus the offset exceeds the length of the target array, in which case an exception is thrown.

`typedarray`  
If the source array is a typed array, the two arrays may share the same underlying [`ArrayBuffer`](../arraybuffer); the JavaScript engine will intelligently **copy** the source range of the buffer to the destination range.

 `offset` <span class="badge inline optional">Optional</span>   
The offset into the target array at which to begin writing values from the source array. If this value is omitted, 0 is assumed (that is, the source array will overwrite values in the target array starting at index 0).

### Exceptions

A [`RangeError`](../rangeerror), if the `offset` is set such as it would store beyond the end of the typed array.

Examples
--------

### Using set()

    var buffer = new ArrayBuffer(8);
    var uint8 = new Uint8Array(buffer);

    uint8.set([1, 2, 3], 3);

    console.log(uint8); // Uint8Array [ 0, 0, 0, 1, 2, 3, 0, 0 ]

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="#">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-%typedarray%.prototype.set-array-offset</span></a></td></tr></tbody></table>

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

`set`

7

14

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

See also
--------

-   [JavaScript typed arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Typed_arrays)
-   [`TypedArray`](../typedarray)
-   [`ArrayBuffer`](../arraybuffer)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/set" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/set</a>
