# ReadableStreamDefaultController

The `ReadableStreamDefaultController` interface of the [Streams API](streams_api) represents a controller allowing control of a [`ReadableStream`](readablestream)'s state and internal queue. Default controllers are for streams that are not byte streams.

## Constructor

None. `ReadableStreamDefaultController` instances are created automatically during `ReadableStream` construction.

## Properties

[`ReadableStreamDefaultController.desiredSize`](readablestreamdefaultcontroller/desiredsize) <span class="badge inline readonly">Read only </span>  
Returns the desired size required to fill the stream's internal queue.

## Methods

[`ReadableStreamDefaultController.close()`](readablestreamdefaultcontroller/close)  
Closes the associated stream.

[`ReadableStreamDefaultController.enqueue()`](readablestreamdefaultcontroller/enqueue)  
Enqueues a given chunk in the associated stream.

[`ReadableStreamDefaultController.error()`](readablestreamdefaultcontroller/error)  
Causes any future interactions with the associated stream to error.

## Examples

In the following simple example, a custom `ReadableStream` is created using a constructor (see our [Simple random stream example](https://mdn.github.io/dom-examples/streams/simple-random-stream/) for the full code). The `start()` function generates a random string of text every second and enqueues it into the stream. A `cancel()` function is also provided to stop the generation if [`ReadableStream.cancel()`](readablestream/cancel) is called for any reason.

Note that a [`ReadableStreamDefaultController`](readablestreamdefaultcontroller) object is provided as the parameter of the `start()` and `pull()` functions.

When a button is pressed, the generation is stopped, the stream is closed using [`ReadableStreamDefaultController.close()`](readablestreamdefaultcontroller/close), and another function is run, which reads the data back out of the stream.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#rs-default-controller-class">Streams<br />
<span class="small">The definition of 'ReadableStreamDefaultController' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`ReadableStreamDefaultController`

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

`close`

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

`desiredSize`

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

`error`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ReadableStreamDefaultController" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ReadableStreamDefaultController</a>
