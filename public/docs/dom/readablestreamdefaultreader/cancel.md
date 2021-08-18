# ReadableStreamDefaultReader.cancel()

The `cancel()` method of the [`ReadableStreamDefaultReader`](../readablestreamdefaultreader) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves when the stream is canceled. Calling this method signals a loss of interest in the stream by a consumer.

Cancel is used when you've completely finished with the stream and don't need any more data from it, even if there are chunks enqueued waiting to be read. That data is lost after cancel is called, and the stream is not readable any more. To read those chunks still and not completely get rid of the stream, you'd use [`ReadableStreamDefaultController.close()`](../readablestreamdefaultcontroller/close).

**Note**: If the reader is active, the `cancel()` method behaves the same as that for the associated stream ([`ReadableStream.cancel()`](../readablestream/cancel)).

## Syntax

    var promise = readableStreamDefaultReader.cancel(reason);

### Parameters

reason <span class="badge inline optional">Optional</span>  
A human-readable reason for the cancellation. This value may or may not be used.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise), which fulfills with the value given in the `reason` parameter.

### Exceptions

TypeError  
The source object is not a `ReadableStreamDefaultReader`, or the stream has no owner.

## Examples

In the following simple example, a previously-created custom `ReadableStream` is read using a [`ReadableStreamDefaultReader`](../readablestreamdefaultreader) created using `getReader()`. (this code is based on our [Simple random stream example](https://mdn.github.io/dom-examples/streams/simple-random-stream/)). Each chunk is read sequentially and output to the UI, until the stream has finished being read, at which point we return out of the recursive function and print the entire stream to another part of the UI.

When the stream is done (`if (done)`), we run `reader.cancel()` to cancel the stream, signalling that we don't need to use it any more.

    function fetchStream() {
      const reader = stream.getReader();
      let charsReceived = 0;

      // read() returns a promise that resolves
      // when a value has been received
      reader.read().then(function processText({ done, value }) {
        // Result objects contain two properties:
        // done  - true if the stream has already given you all its data.
        // value - some data. Always undefined when done is true.
        if (done) {
          console.log("Stream complete");
          reader.cancel();
          para.textContent = result;
          return;
        }

        // value for fetch streams is a Uint8Array
        charsReceived += value.length;
        const chunk = value;
        let listItem = document.createElement('li');
        listItem.textContent = 'Received ' + charsReceived + ' characters so far. Current chunk = ' + chunk;
        list2.appendChild(listItem);

        result += chunk;

        // Read some more, and call this function again
        return reader.read().then(processText);
      });
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#default-reader-cancel">Streams<br />
<span class="small">The definition of 'cancel()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`cancel`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ReadableStreamDefaultReader/cancel" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ReadableStreamDefaultReader/cancel</a>
