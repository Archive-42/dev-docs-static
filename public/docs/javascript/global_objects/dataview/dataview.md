DataView() constructor
======================

The `DataView()` constructor is used to create [`DataView`](../dataview) objects.

Syntax
------

    new DataView(buffer)
    new DataView(buffer, byteOffset)
    new DataView(buffer, byteOffset, byteLength)

### Parameters

`buffer`  
An existing [`ArrayBuffer`](../arraybuffer) or [`SharedArrayBuffer`](../sharedarraybuffer) to use as the storage backing the new `DataView` object.

 `byteOffset` <span class="badge inline optional">Optional</span>   
The offset, in bytes, to the first byte in the above buffer for the new view to reference. If unspecified, the buffer view starts with the first byte.

 `byteLength` <span class="badge inline optional">Optional</span>   
The number of elements in the byte array. If unspecified, the view's length will match the buffer's length.

### Return value

A new `DataView` object representing the specified data buffer. (That probably wasn't a very helpful description.)

You can think of the returned object as an "interpreter" of the array buffer of bytes — it knows how to convert numbers to fit within the buffer correctly, both when reading and writing to it. This means handling integer and float conversion, endianness, and other details of representing numbers in binary form.

### Exceptions

[`RangeError`](../rangeerror)  
Thrown if the `byteOffset` or `byteLength` parameter values result in the view extending past the end of the buffer.

For example, if the buffer is 16 bytes long, the `byteOffset` is 8, and the `byteLength` is 10, this error is thrown because the resulting view tries to extend 2 bytes past the total length of the buffer.

Examples
--------

### Using DataView

    var buffer = new ArrayBuffer(16);
    var view = new DataView(buffer, 0);

    view.setInt16(1, 42);
    view.getInt16(1); // 42

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-dataview-constructor">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-dataview-constructor</span></a></td></tr></tbody></table>

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

`DataView`

9

12

15

10

12.1

5.1

4

18

15

12.1

4.2

1.0

`new_required`

11

13

40

No

15

5.1

≤37

18

40

14

5.1

1.0

`sharedarraybuffer_support`

68

60-63

Chrome disabled SharedArrayBuffer on January 5, 2018 to help reduce the efficacy of [speculative side-channel attacks](https://www.chromium.org/Home/chromium-security/ssca). This was a temporary removal while mitigations were put in place.

79

79

57

Support was disabled by default to mitigate [speculative execution side-channel attacks (Mozilla Security Blog)](https://blog.mozilla.org/security/2018/01/03/mitigations-landing-new-class-timing-attack/).

55-57

46-55

No

No

10.1-11

60-63

Chrome disabled SharedArrayBuffer on January 5, 2018 to help reduce the efficacy of [speculative side-channel attacks](https://www.chromium.org/Home/chromium-security/ssca). This is intended as a temporary measure until other mitigations are in place.

60-63

Chrome disabled SharedArrayBuffer on January 5, 2018 to help reduce the efficacy of [speculative side-channel attacks](https://www.chromium.org/Home/chromium-security/ssca). This is intended as a temporary measure until other mitigations are in place.

79

57

Support was disabled by default to mitigate [speculative execution side-channel attacks (Mozilla Security Blog)](https://blog.mozilla.org/security/2018/01/03/mitigations-landing-new-class-timing-attack/).

55-57

46-55

No

10.3-11

No

Chrome disabled SharedArrayBuffer on January 5, 2018 to help reduce the efficacy of [speculative side-channel attacks](https://www.chromium.org/Home/chromium-security/ssca). This is intended as a temporary measure until other mitigations are in place.

See also
--------

-   [`DataView`](../dataview)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/DataView/DataView" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/DataView/DataView</a>
