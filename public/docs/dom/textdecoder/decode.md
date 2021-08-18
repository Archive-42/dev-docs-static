TextDecoder.prototype.decode()
==============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `TextDecoder.prototype.decode()` method returns a [`DOMString`](../domstring) containing the text, given in parameters, decoded with the specific method for that `TextDecoder` object.

Syntax
------

    b1 = decoder.decode(buffer, options);
    b2 = decoder.decode(buffer);
    b3 = decoder.decode();

### Parameters

 `buffer` <span class="badge inline optional">Optional</span>   
Is either an `ArrayBuffer` or an [`ArrayBufferView`](../arraybufferview) containing the text to decode.

 `options` <span class="badge inline optional">Optional</span>   
Is a `TextDecodeOptions` dictionary with the property:

`stream`  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) flag indicating that additional data will follow in subsequent calls to decode(). Set to true if processing the data in chunks, and false for the final chunk or if the data is not chunked. It defaults to false.

Example
-------

This example encodes and decodes the euro symbol, €.

### HTML

    <p>Encoded value: <span id="encoded-value"></span></p>
    <p>Decoded value: <span id="decoded-value"></span></p>

### JavaScript

    const encoder = new TextEncoder();
    const array = encoder.encode('€'); // Uint8Array(3) [226, 130, 172]
    document.getElementById('encoded-value').textContent = array;

    const decoder = new TextDecoder();
    const str = decoder.decode(array); // String "€"
    document.getElementById('decoded-value').textContent = str;

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://encoding.spec.whatwg.org/#dom-textdecoder-decode">Encoding<br />
<span class="small">The definition of 'TextDecoder.decode()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

See also
--------

-   The [`TextDecoder`](../textdecoder) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TextDecoder/decode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TextDecoder/decode</a>
