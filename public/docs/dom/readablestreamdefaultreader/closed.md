# ReadableStreamDefaultReader.closed

The `closed` read-only property of the [`ReadableStreamDefaultReader`](../readablestreamdefaultreader) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that fulfills when the stream closes or the reader's lock is released, or rejects if the stream throws an error. This property enables you to write code that responds to an end to the streaming process.

## Syntax

    var closed = readableStreamDefaultReader.closed;

### Value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise).

## Examples

In this snippet, a previously-created reader is queried to see if the stream has been closed. When it is closed, the promise fulfills and the message is logged to the console.

    reader.closed.then(() => {
      console.log('reader closed');
    })

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#default-reader-closed">Streams<br />
<span class="small">The definition of 'closed' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`closed`

?

?

65

No

?

No

?

?

65

?

No

?

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ReadableStreamDefaultReader/closed" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ReadableStreamDefaultReader/closed</a>
