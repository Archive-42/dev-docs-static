# Compression Streams API

The **Compression Streams API** provides a JavaScript API for compressing and decompressing streams of data using the gzip or deflate formats.

Built in compression means that JavaScript applications will not need to include a compression library, which makes the download size of the application smaller.

## Interfaces

[`CompressionStream`](compressionstream)  
Compresses a stream of data.

[`DecompressionStream`](decompressionstream)  
Decompresses a stream of data.

## Examples

In this example a stream is compressed using gzip compression.

    const compressedReadableStream = inputReadableStream.pipeThrough(new CompressionStream('gzip'));

In the following example a function decompresses a blob using gzip.

    async function DecompressBlob(blob) {
      const ds = new DecompressionStream('gzip');
      const decompressedStream = blob.stream().pipeThrough(ds);
      return await new Response(decompressedStream).blob();
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/compression/">Compression Streams</a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`Compression_Streams_API`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Compression_Streams_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Compression_Streams_API</a>
