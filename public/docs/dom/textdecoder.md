TextDecoder
===========

The `TextDecoder` interface represents a decoder for a specific text encoding, such as `UTF-8`, `ISO-8859-2`, `KOI8-R`, `GBK`, etc. A decoder takes a stream of bytes as input and emits a stream of code points.

**Note:** This feature is available in [Web Workers](web_workers_api).

Examples
--------

### Representing text with typed arrays

This example shows how to decode a Chinese/Japanese character <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACkAAAAgCAAAAACqBA7iAAAACXBIWXMAABYlAAAWJQFJUiTwAAAASUlEQVR4nGP4TyxgoJNKBqzasaok3kwaqmTAKgpiYoKBdCdtVCL7iQEhiB0QsIlY2wmrREtD6FwUKTxRRLaZw08l9UMJPxgqKgFknKCY7ZqzGQAAAABJRU5ErkJggg==" width="41" height="32" />, as represented by five different typed arrays: [`Uint8Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint8Array), [`Int8Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Int8Array), [`Uint16Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint16Array), [`Int16Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Int16Array), and [`Int32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Int32Array).

    let utf8decoder = new TextDecoder(); // default 'utf-8' or 'utf8'

    let u8arr = new Uint8Array([240, 160, 174, 183]);
    let i8arr = new Int8Array([-16, -96, -82, -73]);
    let u16arr = new Uint16Array([41200, 47022]);
    let i16arr = new Int16Array([-24336, -18514]);
    let i32arr = new Int32Array([-1213292304]);

    console.log(utf8decoder.decode(u8arr));
    console.log(utf8decoder.decode(i8arr));
    console.log(utf8decoder.decode(u16arr));
    console.log(utf8decoder.decode(i16arr));
    console.log(utf8decoder.decode(i32arr));

### Handling non-UTF8 text

In this example, we decode the Russian text "Привет, мир!", which means "Hello, world." In our [`TextDecoder()`](textdecoder/textdecoder) constructor, we specify the Windows-1251 character encoding, which is appropriate for Cyrillic script.

    let win1251decoder = new TextDecoder('windows-1251');
    let bytes = new Uint8Array([207, 240, 232, 226, 229, 242, 44, 32, 236, 232, 240, 33]);
    console.log(win1251decoder.decode(bytes)); // Привет, мир!

Constructor
-----------

[`TextDecoder()`](textdecoder/textdecoder)  
Returns a newly constructed `TextDecoder` that will generate a code point stream with the decoding method specified in parameters.

Properties
----------

*The `TextDecoder` interface doesn't inherit any properties.*

 [`TextDecoder.prototype.encoding`](textdecoder/encoding)<span class="badge inline readonly">Read only </span>   
Is a [`DOMString`](domstring) containing the name of the decoder, that is a string describing the method the `TextDecoder` will use.

 <span class="page-not-created">`TextDecoder.prototype.fatal`</span><span class="badge inline readonly">Read only </span>   
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the error mode is fatal.

 <span class="page-not-created">`TextDecoder.prototype.ignoreBOM`</span><span class="badge inline readonly">Read only </span>   
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the byte order marker is ignored.

Methods
-------

*The `TextDecoder` interface doesn't inherit any method*.

[`TextDecoder.prototype.decode()`](textdecoder/decode)  
Returns a [`DOMString`](domstring) containing the text decoded with the method of the specific `TextDecoder` object.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://encoding.spec.whatwg.org/#interface-textdecoder">Encoding<br />
<span class="small">The definition of 'TextDecoder' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`TextDecoder`

38

≤79

19

18

Implemented a slightly different version of the spec.

No

25

10.1

38

38

19

18

Implemented a slightly different version of the spec.

Yes

10.3

3.0

`TextDecoder`

38

≤79

19

18

Implemented a slightly different version of the spec.

No

25

10.1

38

38

19

18

Implemented a slightly different version of the spec.

?

10.3

3.0

`decode`

38

≤79

19

18

Implemented a slightly different version of the spec.

No

25

10.1

38

38

19

18

Implemented a slightly different version of the spec.

Yes

10.3

3.0

`encoding`

38

≤79

19

18

Implemented a slightly different version of the spec.

No

25

10.1

38

38

19

18

Implemented a slightly different version of the spec.

Yes

10.3

3.0

`fatal`

Yes

≤79

Yes

No

Yes

10.1

Yes

Yes

Yes

Yes

10.3

Yes

`ignoreBOM`

Yes

≤79

Yes

No

Yes

10.1

Yes

Yes

Yes

Yes

10.3

Yes

`worker_support`

38

≤79

20

No

25

10.1

38

38

20

?

10.3

3.0

See also
--------

-   The [`TextEncoder`](textencoder) interface describing the inverse operation.
-   [`StringView`](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/Code_snippets/StringView) – a C-like representation of strings based on typed arrays
-   A [shim](https://code.google.com/p/stringencoding/) allowing to use this interface in browsers that don't support it.
-   `Components.utils.importGlobalProperties`
-   [Node.js supports global export from v11.0.0](https://nodejs.org/api/util.html#util_class_util_textdecoder)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TextDecoder" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TextDecoder</a>
