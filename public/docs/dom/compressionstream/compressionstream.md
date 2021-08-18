# CompressionStream.CompressionStream()

The `CompressionStream()` constructor creates a new [`CompressionStream`](../compressionstream) object which compresses a stream of data.

## Syntax

    let CompressionStream = new CompressionStream(format);

### Parameters

`format`  
One of the following allowed compression formats:

- `"gzip"`
- `"deflate"`

## Exceptions

[`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError)  
Thrown if the format passed to the constructor is not supported.

## Examples

In this example a stream is compressed using gzip compression.

    const compressedReadableStream = inputReadableStream.pipeThrough(new CompressionStream('gzip'));

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/compression/#dom-compressionstream-compressionstream">Compression Streams<br />
<span class="small">The definition of 'CompressionStream()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CompressionStream/CompressionStream" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CompressionStream/CompressionStream</a>
