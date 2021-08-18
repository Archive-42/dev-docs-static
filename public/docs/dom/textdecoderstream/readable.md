TextDecoderStream.readable
==========================

The `readable` read-only property of the [`TextDecoderStream`](../textdecoderstream) interface returns a [`ReadableStream`](../readablestream).

Syntax
------

    var readable = TextDecoderStream.readable;

### Value

A [`ReadableStream`](../readablestream).

Examples
--------

This example shows how to return a [`ReadableStream`](../readablestream) from a `TextDecoderStream`.

    stream = new TextDecoderStream();
    console.log(stream.readable); //a ReadableStream

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#dom-generictransformstream-readable">Streams<br />
<span class="small">The definition of 'readable' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`readable`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TextDecoderStream/readable" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TextDecoderStream/readable</a>
