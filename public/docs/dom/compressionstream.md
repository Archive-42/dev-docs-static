# CompressionStream

The `CompressionStream` interface of the [Compression Streams API](compression_streams_api) is an API for compressing a stream of data.

## Constructor

[`CompressionStream.CompressionStream()`](compressionstream/compressionstream)  
Creates a new `CompressionStream`

## Properties

[`CompressionStream.readable`](compressionstream/readable)  
Returns the [`ReadableStream`](readablestream) instance controlled by this object.

[`CompressionStream.writable`](compressionstream/writable)  
Returns the [`WritableStream`](writablestream) instance controlled by this object.

## Examples

In this example a stream is compressed using gzip compression.

    const compressedReadableStream = inputReadableStream.pipeThrough(new CompressionStream('gzip'));

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/compression/#compression-stream">Compression Streams<br />
<span class="small">The definition of 'CompressionStream' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`CompressionStream`

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

`CompressionStream`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CompressionStream" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CompressionStream</a>
