TextDecoderStream.ignoreBOM
===========================

The `ignoreBOM` read-only property of the [`TextDecoderStream`](../textdecoderstream) interface returns a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating if the byte order mark (BOM) is to be ignored.

Syntax
------

    var ignoreBOM = TextDecoderStream.ignoreBOM;

### Value

A [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean), initially `false`

Examples
--------

    stream = new TextDecoderStream();
    console.log(stream.ignoreBOM); // returns false

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://encoding.spec.whatwg.org/#textdecoder-ignore-bom-flag">Encoding<br />
<span class="small">The definition of 'TextDecoderStream.ignoreBOM' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ignoreBOM`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TextDecoderStream/ignoreBOM" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TextDecoderStream/ignoreBOM</a>
