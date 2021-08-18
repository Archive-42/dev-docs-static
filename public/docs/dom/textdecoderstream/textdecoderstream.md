TextDecoderStream.TextDecoderStream()
=====================================

The `TextDecoderStream()` constructor creates a new [`TextDecoderStream`](../textdecoderstream) object which is used to convert a stream of text in a binary encoding into strings.

Syntax
------

    var TextDecoderStream = new TextDecoderStream(label,options);

### Parameters

label  
A [`DOMString`](../domstring) defaulting to `utf-8`. This may be [any valid label](../encoding_api/encodings).

 `options`<span class="badge inline optional">Optional</span>   
A `TextDecoderOptions` dictionary with the property:

`fatal`  
A [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating the error mode. If true then a [`DOMException`](../domexception) will be thrown if the decoder encounters an error. Defaults to `false`.

Examples
--------

The following example demonstrates how to decode binary data retrieved from a <span class="page-not-created">`fetch`</span> call. The data will be interpreted as UTF-8, as no `label` has been passed.

    const response = await fetch("https://example.com");
    const stream = response.body.pipeThrough(new TextDecoderStream());

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://encoding.spec.whatwg.org/#dom-textdecoderstream">Encoding<br />
<span class="small">The definition of 'TextDecoderStream()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`TextDecoderStream`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TextDecoderStream/TextDecoderStream" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TextDecoderStream/TextDecoderStream</a>
