TextDecoderStream.encoding
==========================

The `encoding` read-only property of the [`TextDecoderStream`](../textdecoderstream) interface returns a [`DOMString`](../domstring) containing the name of the encoding algorithm used by the specific encoder.

Syntax
------

    var encoding = TextDecoderStream.encoding;

### Value

A [`DOMString`](../domstring), ASCII lowercased.

Examples
--------

Returning the value of `encoding` from a `TextDecoderStream`.

    stream = new TextDecoderStream();
    console.log(stream.encoding); // returns the default "utf-8"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://encoding.spec.whatwg.org/#dom-textdecoder-encoding">Encoding<br />
<span class="small">The definition of 'TextDecoderStream.encoding' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`encoding`

71

79

No

No

58

14.1

71

71

No

50

14.5

10.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TextDecoderStream/encoding" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TextDecoderStream/encoding</a>
