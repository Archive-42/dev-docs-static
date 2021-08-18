# ReadableStreamBYOBReader

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `ReadableStreamBYOBReader` interface of the [Streams API](streams_api) represents a BYOB ("bring your own buffer") reader that can be used to read stream data supplied by the developer (e.g. a custom [`ReadableStream()`](readablestream/readablestream) constructor).

## Constructor

[`ReadableStreamBYOBReader()`](readablestreambyobreader/readablestreambyobreader)  
Creates and returns a `ReadableStreamBYOBReader` object instance.

## Properties

[`ReadableStreamBYOBReader.closed`](readablestreambyobreader/closed) <span class="badge inline readonly">Read only </span>  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that fulfills when the stream closes or the reader's lock is released, or rejects if the stream throws an error. This property enables you to write code that responds to an end to the streaming process.

## Methods

[`ReadableStreamBYOBReader.cancel()`](readablestreambyobreader/cancel)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves when the stream is canceled. Calling this method signals a loss of interest in the stream by a consumer. The supplied `reason` argument will be given to the underlying source, which may or may not use it.

[`ReadableStreamBYOBReader.read()`](readablestreambyobreader/read)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with an object indicating the state of the stream: either the next chunk in the stream or an indication that the stream is closed.

[`ReadableStreamBYOBReader.releaseLock()`](readablestreambyobreader/releaselock)  
Releases the reader's lock on the stream.

## Examples

TBD.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#byob-reader-class">Streams<br />
<span class="small">The definition of 'ReadableStreamBYOBReader' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`ReadableStreamBYOBReader`

No

No

No

No

No

No

No

No

No

No

No

No

`ReadableStreamBYOBReader`

No

No

No

No

No

No

No

No

No

No

No

No

`cancel`

No

No

No

No

No

No

No

No

No

No

No

No

`closed`

No

No

No

No

No

No

No

No

No

No

No

No

`read`

No

No

No

No

No

No

No

No

No

No

No

No

`releaseLock`

No

No

No

No

No

No

No

No

No

No

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ReadableStreamBYOBReader" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ReadableStreamBYOBReader</a>
