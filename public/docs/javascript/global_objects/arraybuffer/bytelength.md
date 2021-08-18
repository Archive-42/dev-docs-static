ArrayBuffer.prototype.byteLength
================================

The `byteLength` accessor property represents the length of an [`ArrayBuffer`](../arraybuffer) in bytes.

Description
-----------

The `byteLength` property is an accessor property whose set accessor function is `undefined`, meaning that you can only read this property. The value is established when the array is constructed and cannot be changed. This property returns 0 if this `ArrayBuffer` has been detached.

Examples
--------

### Using byteLength

    var buffer = new ArrayBuffer(8);
    buffer.byteLength; // 8

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-get-arraybuffer.prototype.bytelength">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-get-arraybuffer.prototype.bytelength</span></a></td></tr></tbody></table>

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

`byteLength`

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

See also
--------

-   [`ArrayBuffer`](../arraybuffer)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer/byteLength" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer/byteLength</a>
