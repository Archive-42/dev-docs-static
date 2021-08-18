# Blob.arrayBuffer()

The `arrayBuffer()` method in the [`Blob`](../blob) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with the contents of the blob as binary data contained in an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer).

## Syntax

    var bufferPromise = blob.arrayBuffer();

    blob.arrayBuffer().then(buffer => /* process the ArrayBuffer */);

    var buffer = await blob.arrayBuffer();

### Parameters

None.

### Returns

A promise that resolves with an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) that contains the blob's data in binary form.

### Exceptions

While this method doesn't throw exceptions, it may reject the promise. This can happen, for example, if the reader used to fetch the blob's data throws an exception. Any exceptions thrown while getting the data will be converted into rejections.

## Usage notes

While similar to the [`FileReader.readAsArrayBuffer()`](../filereader/readasarraybuffer) method, `arrayBuffer()` returns a promise rather than being an event-based API, as is the case with the `FileReader` interface's method.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/FileAPI/#dom-blob-arraybuffer">File API<br />
<span class="small">The definition of 'Blob.arrayBuffer()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`arrayBuffer`

76

79

69

No

No

14

76

76

No

54

14

12.0

## See also

- [`Body.arrayBuffer()`](../body/arraybuffer)
- [Streams API](../streams_api)
- [`FileReader.readAsArrayBuffer()`](../filereader/readasarraybuffer)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Blob/arrayBuffer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Blob/arrayBuffer</a>
