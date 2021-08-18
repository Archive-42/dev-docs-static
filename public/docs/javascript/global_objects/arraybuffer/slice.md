ArrayBuffer.prototype.slice()
=============================

The `slice()` method returns a new `ArrayBuffer` whose contents are a copy of this `ArrayBuffer`'s bytes from `begin`, inclusive, up to `end`, exclusive.

Syntax
------

    slice(begin)
    slice(begin, end)

### Parameters

`begin`  
Zero-based byte index at which to begin slicing.

 `end` <span class="badge inline optional">Optional</span>   
Byte index before which to end slicing. If end is unspecified, the new `ArrayBuffer` contains all bytes from begin to the end of this `ArrayBuffer`. If negative, it will make the Byte index begin from the last Byte.

### Return value

A new [`ArrayBuffer`](../arraybuffer) object.

Description
-----------

The `slice()` method copies up to, but not including, the byte indicated by the `end` parameter. If either `begin` or `end` is negative, it refers to an index from the end of the array, as opposed to from the beginning.

The range specified by the `begin` and `end` parameters is clamped to the valid index range for the current array. If the computed length of the new `ArrayBuffer` would be negative, it is clamped to zero.

Examples
--------

### Copying an ArrayBuffer

    const buf1 = new ArrayBuffer(8);
    const buf2 = buf1.slice(0);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-arraybuffer.prototype.slice">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-arraybuffer.prototype.slice</span></a></td></tr></tbody></table>

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

`slice`

17

12

12

The non-standard `ArrayBuffer.slice()` method has been removed in Firefox 53 (but the standardized version `ArrayBuffer.prototype.slice()` is kept.

11

12.1

6

≤37

18

14

The non-standard `ArrayBuffer.slice()` method has been removed in Firefox 53 (but the standardized version `ArrayBuffer.prototype.slice()` is kept.

12.1

6

1.0

See also
--------

-   [`ArrayBuffer`](../arraybuffer)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer/slice" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer/slice</a>
