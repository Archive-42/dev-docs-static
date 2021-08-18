DataView.prototype.byteLength
=============================

The `byteLength` accessor property represents the length (in bytes) of this view from the start of its [`ArrayBuffer`](../arraybuffer) or [`SharedArrayBuffer`](../sharedarraybuffer).

Description
-----------

The `byteLength` property is an accessor property whose set accessor function is `undefined`, meaning that you can only read this property. The value is established when an `DataView` is constructed and cannot be changed. If the `DataView` is not specifying an offset or a `byteLength`, the `byteLength` of the referenced `ArrayBuffer` or `SharedArrayBuffer` will be returned.

Examples
--------

### Using the byteLength property

    var buffer = new ArrayBuffer(8);
    var dataview = new DataView(buffer);
    dataview.byteLength; // 8 (matches the byteLength of the buffer)

    var dataview2 = new DataView(buffer, 1, 5);
    dataview2.byteLength; // 5 (as specified when constructing the DataView)

    var dataview3 = new DataView(buffer, 2);
    dataview3.byteLength; // 6 (due to the offset of the constructed DataView)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-get-dataview.prototype.bytelength">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-get-dataview.prototype.bytelength</span></a></td></tr></tbody></table>

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

See also
--------

-   [`DataView`](../dataview)
-   [`ArrayBuffer`](../arraybuffer)
-   [`SharedArrayBuffer`](../sharedarraybuffer)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/DataView/byteLength" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/DataView/byteLength</a>
