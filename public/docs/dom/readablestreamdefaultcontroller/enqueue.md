# ReadableStreamDefaultController.enqueue()

The `enqueue()` method of the [`ReadableStreamDefaultController`](../readablestreamdefaultcontroller) interface enqueues a given chunk in the associated stream.

## Syntax

    readableStreamDefaultController.enqueue(chunk);

### Parameters

_chunk_  
The chunk to enqueue.

### Return value

`undefined`.

### Exceptions

TypeError  
The source object is not a `ReadableStreamDefaultController`.

## Examples

In the following simple example, a custom `ReadableStream` is created using a constructor (see our [Simple random stream example](https://mdn.github.io/dom-examples/streams/simple-random-stream/) for the full code). The `start()` function generates a random string of text every second and enqueues it into the stream — see `controller.enqueue(string)`. A `cancel()` function is also provided to stop the generation if [`ReadableStream.cancel()`](../readablestream/cancel) is called for any reason.

When a button is pressed, the generation is stopped, the stream is closed using [`ReadableStreamDefaultController.close()`](close), and another function is run, which reads the data back out of the stream.

    const stream = new ReadableStream({
      start(controller) {
        interval = setInterval(() => {
          let string = randomChars();

          // Add the string to the stream
          controller.enqueue(string);

          // show it on the screen
          let listItem = document.createElement('li');
          listItem.textContent = string;
          list1.appendChild(listItem);
        }, 1000);

        button.addEventListener('click', function() {
          clearInterval(interval);
          fetchStream();
          controller.close();
        })
      },
      pull(controller) {
        // We don't really need a pull in this example
      },
      cancel() {
        // This is called if the reader cancels,
        // so we should stop generating strings
        clearInterval(interval);
      }
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#rs-default-controller-enqueue">Streams<br />
<span class="small">The definition of 'enqueue()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`enqueue`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ReadableStreamDefaultController/enqueue" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ReadableStreamDefaultController/enqueue</a>
