# CompressionStream.readable

The `readable` read-only property of the [`CompressionStream`](../compressionstream) interface returns a [`ReadableStream`](../readablestream).

## Syntax

    let stream = CompressionStream.readable;

### Value

A [`ReadableStream`](../readablestream).

## Examples

The following example returns a [`ReadableStream`](../readablestream) from a `CompressionStream`.

    let stream = new CompressionStream('gzip');
    console.log(stream.readable); //a ReadableStream

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#dom-generictransformstream-readable">Streams<br />
<span class="small">The definition of 'readable' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

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

80

80

No

No

67

No

80

80

No

57

No

13.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CompressionStream/readable" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CompressionStream/readable</a>
