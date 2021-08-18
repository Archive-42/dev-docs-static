# ReadableStreamDefaultReader

The `ReadableStreamDefaultReader` interface of the [Streams API](streams_api) represents a default reader that can be used to read stream data supplied from a network (e.g. a fetch request).

## Constructor

[`ReadableStreamDefaultReader()`](readablestreamdefaultreader/readablestreamdefaultreader)  
Creates and returns a `ReadableStreamDefaultReader` object instance.

## Properties

[`ReadableStreamDefaultReader.closed`](readablestreamdefaultreader/closed) <span class="badge inline readonly">Read only </span>  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that fulfills when the stream closes or the reader's lock is released, or rejects if the stream throws an error. This property enables you to write code that responds to an end to the streaming process.

## Methods

[`ReadableStreamDefaultReader.cancel()`](readablestreamdefaultreader/cancel)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves when the stream is canceled. Calling this method signals a loss of interest in the stream by a consumer. The supplied `reason` argument will be given to the underlying source, which may or may not use it.

[`ReadableStreamDefaultReader.read()`](readablestreamdefaultreader/read)  
Returns a promise providing access to the next chunk in the stream's internal queue.

[`ReadableStreamDefaultReader.releaseLock()`](readablestreamdefaultreader/releaselock)  
Releases the reader's lock on the stream.

## Examples

In the following example, an artifical [`Response`](response) is created to stream HTML fragments fetched from another resource to the browser.

It demonstrates the usage of a [`ReadableStream`](readablestream) in combination with a [`Uint8Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint8Array).

    fetch("https://www.example.org/").then((response) => {
      const reader = response.body.getReader();
      const stream = new ReadableStream({
        start(controller) {
          // The following function handles each data chunk
          function push() {
            // "done" is a Boolean and value a "Uint8Array"
            return reader.read().then(({ done, value }) => {
              // Is there no more data to read?
              if (done) {
                // Tell the browser that we have finished sending data
                controller.close();
                return;
              }

              // Get the data and send it to the browser via the controller
              controller.enqueue(value);
              push();
            });
          };

          push();
        }
      });

      return new Response(stream, { headers: { "Content-Type": "text/html" } });
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#default-reader-class">Streams<br />
<span class="small">The definition of 'ReadableStreamDefaultReader' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`ReadableStreamDefaultReader`

52

≤79

65

No

39

No

52

52

65

41

No

6.0

`ReadableStreamDefaultReader`

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

`read`

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

`releaseLock`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ReadableStreamDefaultReader" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ReadableStreamDefaultReader</a>
