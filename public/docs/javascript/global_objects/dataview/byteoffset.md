DataView.prototype.byteOffset
=============================

The `byteOffset` accessor property represents the offset (in bytes) of this view from the start of its [`ArrayBuffer`](../arraybuffer) or [`SharedArrayBuffer`](../sharedarraybuffer).

Description
-----------

The `byteOffset` property is an accessor property whose set accessor function is `undefined`, meaning that you can only read this property. The value is established when an `DataView` is constructed and cannot be changed.

Examples
--------

### Using the byteOffset property

    var buffer = new ArrayBuffer(8);
    var dataview = new DataView(buffer);
    dataview.byteOffset; // 0 (no offset specified)

    var dataview2 = new DataView(buffer, 3);
    dataview2.byteOffset; // 3 (as specified when constructing the DataView)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-get-dataview.prototype.byteoffset">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-get-dataview.prototype.byteoffset</span></a></td></tr></tbody></table>

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

`byteOffset`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/DataView/byteOffset" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/DataView/byteOffset</a>
