# DecompressionStream

The `DecompressionStream` interface of the [Compression Streams API](compression_streams_api) is an API for decompressing a stream of data.

## Constructor

[`DecompressionStream.DecompressionStream()`](decompressionstream/decompressionstream)  
Creates a new `DecompressionStream`

## Properties

[`DecompressionStream.readable`](decompressionstream/readable)  
Returns the [`ReadableStream`](readablestream) instance controlled by this object.

[`DecompressionStream.writable`](decompressionstream/writable)  
Returns the [`WritableStream`](writablestream) instance controlled by this object.

## Examples

In this example a blob is decompressed using gzip compression.

    const ds = new DecompressionStream('gzip');
    const decompressedStream = blob.stream().pipeThrough(ds);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/compression/#decompression-stream">Compression Streams<br />
<span class="small">The definition of 'DecompressionStream' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`DecompressionStream`

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

`DecompressionStream`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DecompressionStream" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DecompressionStream</a>
