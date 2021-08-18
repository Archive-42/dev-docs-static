# DecompressionStream.DecompressionStream()

The `DecompressionStream()` constructor creates a new [`DecompressionStream`](../decompressionstream) object which decompresses a stream of data.

## Syntax

    let DecompressionStream = new DecompressionStream(format);

### Parameters

`format`  
One of the following compression formats:

- `"gzip"`
- `"deflate"`

## Exceptions

[`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError)  
Thrown if the format passed to the constructor is not supported.

## Examples

In this example a blob is decompressed using gzip compression.

    const ds = new DecompressionStream('gzip');
    const decompressedStream = blob.stream().pipeThrough(ds);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/compression/#dom-decompressionstream-decompressionstream">Compression Streams<br />
<span class="small">The definition of 'DecompressionStream()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DecompressionStream/DecompressionStream" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DecompressionStream/DecompressionStream</a>
