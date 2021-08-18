# CompressionStream.writable

The `writable` read-only property of the [`CompressionStream`](../compressionstream) interface returns a [`WritableStream`](../writablestream).

## Syntax

    let writableStream = CompressionStream.writable;

### Value

A [`WritableStream`](../writablestream).

## Examples

The following example returns a [`WritableStream`](../writablestream) from a `CompressionStream`.

    let stream = new CompressionStream('gzip');
    console.log(stream.writeable); //a WritableStream

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#dom-generictransformstream-writable">Streams<br />
<span class="small">The definition of 'writable' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`writable`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CompressionStream/writable" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CompressionStream/writable</a>
