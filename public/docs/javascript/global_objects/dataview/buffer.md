DataView.prototype.buffer
=========================

The `buffer` accessor property represents the [`ArrayBuffer`](../arraybuffer) or [`SharedArrayBuffer`](../sharedarraybuffer) referenced by the `DataView` at construction time.

Description
-----------

The `buffer` property is an accessor property whose set accessor function is `undefined`, meaning that you can only read this property. The value is established when the `DataView` is constructed and cannot be changed.

Examples
--------

### Using the buffer property

    var buffer = new ArrayBuffer(8);
    var dataview = new DataView(buffer);
    dataview.buffer; // ArrayBuffer { byteLength: 8 }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-get-dataview.prototype.buffer">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-get-dataview.prototype.buffer</span></a></td></tr></tbody></table>

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

`buffer`

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

`sharedarraybuffer_support`

60

79

79

No

47

10.1-11.1

60

60

79

44

10.3-11.3

8.0

See also
--------

-   [`DataView`](../dataview)
-   [`ArrayBuffer`](../arraybuffer)
-   [`SharedArrayBuffer`](../sharedarraybuffer)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/DataView/buffer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/DataView/buffer</a>
