TextDecoder()
=============

The `TextDecoder()` constructor returns a newly created [`TextDecoder`](../textdecoder) object for the encoding specified in parameter.

If the value for *utfLabel* is unknown, or is one of the two values leading to a `'replacement'` decoding algorithm ( "`iso-2022-cn`" or "`iso-2022-cn-ext`"), a [`DOMException`](../domexception) with the `"TypeError"` value is thrown.

Syntax
------

    decoder = new TextDecoder(utfLabel, options);

### Parameters

 `utfLabel`<span class="badge inline optional">Optional</span>   
Is a [`DOMString`](../domstring), defaulting to `"utf-8"`, containing the *label* of the encoder. This may be [any valid label](../encoding_api/encodings).

 `options`<span class="badge inline optional">Optional</span>   
Is a `TextDecoderOptions` dictionary with the property:

`fatal`  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) flag indicating if the [`TextDecoder.decode()`](decode) method must throw a [`DOMException`](../domexception) with the `"EncodingError"` value when an coding error is found. It defaults to `false`.

Example
-------

    var textDecoder1 = new TextDecoder("iso-8859-2");
    var textDecoder2 = new TextDecoder();
    var textDecoder3 = new TextDecoder("csiso2022kr", {fatal: true}); // Allows EncodingError exception to be thrown.
    var textDecoder4 = new TextDecoder("iso-2022-cn"); // Throw a TypeError exception.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://encoding.spec.whatwg.org/#dom-textdecoder">Encoding<br />
<span class="small">The definition of 'TextDecoder()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

?

10.3

3.0

See also
--------

-   The [`TextDecoder`](../textdecoder) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TextDecoder/TextDecoder" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TextDecoder/TextDecoder</a>
