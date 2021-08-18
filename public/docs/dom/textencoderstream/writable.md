TextEncoderStream.writable
==========================

The `writable` read-only property of the [`TextEncoderStream`](../textencoderstream) interface returns a [`WritableStream`](../writablestream).

Syntax
------

    var writable = TextEncoderStream.writable;

### Value

A [`WritableStream`](../writablestream).

Examples
--------

The following example demonstrates how to return a `WritableStream` from a `TextEncoderStream` object.

    stream = new TextEncoderStream();
    console.log(stream.writeable); //a WritableStream

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#dom-generictransformstream-writable">Streams<br />
<span class="small">The definition of 'writable' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`writable`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TextEncoderStream/writable" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TextEncoderStream/writable</a>
