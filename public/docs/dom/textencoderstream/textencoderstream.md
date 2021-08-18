TextEncoderStream.TextEncoderStream()
=====================================

The `TextEncoderStream()` constructor creates a new [`TextEncoderStream`](../textencoderstream) object which is used to convert a stream of strings into bytes using UTF-8 encoding.

Syntax
------

    var TextEncoderStream = new TextEncoderStream();

Examples
--------

In this example a `TextEncoderStream` is created and used to upload a stream of text.

    const body = textStream.pipeThrough(new TextEncoderStream());
    fetch('/dest', { method: 'POST', body, headers: {'Content-Type': 'text/plain; charset=UTF-8'} });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://encoding.spec.whatwg.org/#dom-textencoderstream">Encoding<br />
<span class="small">The definition of 'TextEncoderStream()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`TextEncoderStream`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TextEncoderStream/TextEncoderStream" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TextEncoderStream/TextEncoderStream</a>
