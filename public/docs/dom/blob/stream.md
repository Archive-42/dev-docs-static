# Blob.stream()

The [`Blob`](../blob) interface's `stream()` method returns a [`ReadableStream`](../readablestream) which upon reading returns the data contained within the `Blob`.

## Syntax

    var stream = blob.stream();

### Parameters

None.

### Returns

A [`ReadableStream`](../readablestream) which, upon reading, returns the contents of the `Blob`.

## Usage notes

With `stream()` and the returned [`ReadableStream`](../readablestream), you gain several interesting capabilities:

- Call [`getReader()`](../readablestream/getreader) on the returned stream to get an object to use to read the data from the blob using methods such as the [`ReadableStreamDefaultReader`](../readablestreamdefaultreader) interface's [`read()`](../readablestreamdefaultreader/read) method.
- Call the returned stream's [`pipeTo()`](../readablestream/pipeto) method to pipe the blob's data to a writable stream.
- Call the returned stream's [`tee()`](../readablestream/tee) method to **tee** the readable stream. This returns an array containing two new `ReadableStream` objects, each of which returns the contents of the `Blob`.
- Call the returned stream's [`pipeThrough()`](../readablestream/pipethrough) method to pipe the stream through a [`TransformStream`](../transformstream) or any other readable and writable pair.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/FileAPI/#dom-blob-stream">File API<br />
<span class="small">The definition of 'Blob.stream()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`stream`

76

79

69

No

No

14.1

76

76

No

54

14.5

12.0

## See also

- [`Body.body`](../body/body)
- [Streams API](../streams_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Blob/stream" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Blob/stream</a>
