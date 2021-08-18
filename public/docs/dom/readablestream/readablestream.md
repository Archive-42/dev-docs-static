ReadableStream.ReadableStream()
===============================

The `ReadableStream()` constructor creates and returns a readable stream object from the given handlers.

Syntax
------

    var readableStream = new ReadableStream(underlyingSource[, queuingStrategy]);

### Parameters

underlyingSource <span class="badge inline optional">Optional</span>   
An object containing methods and properties that define how the constructed stream instance will behave. `underlyingSource` can contain the following:

start(controller) <span class="badge inline optional">Optional</span>   
This is a method, called immediately when the object is constructed. The contents of this method are defined by the developer, and should aim to get access to the stream source, and do anything else required to set up the stream functionality. If this process is to be done asynchronously, it can return a promise to signal success or failure. The `controller` parameter passed to this method is a [`ReadableStreamDefaultController`](../readablestreamdefaultcontroller) or a [`ReadableByteStreamController`](../readablebytestreamcontroller), depending on the value of the `type` property. This can be used by the developer to control the stream during set up.

pull(controller) <span class="badge inline optional">Optional</span>   
This method, also defined by the developer, will be called repeatedly when the stream's internal queue of chunks is not full, up until it reaches its high water mark. If `pull()` returns a promise, then it won't be called again until that promise fulfills; if the promise rejects, the stream will become errored. The `controller` parameter passed to this method is a [`ReadableStreamDefaultController`](../readablestreamdefaultcontroller) or a [`ReadableByteStreamController`](../readablebytestreamcontroller), depending on the value of the `type` property. This can be used by the developer to control the stream as more chunks are fetched.

cancel(reason) <span class="badge inline optional">Optional</span>   
This method, also defined by the developer, will be called if the app signals that the stream is to be cancelled (e.g. if [`ReadableStream.cancel()`](cancel) is called). The contents should do whatever is necessary to release access to the stream source. If this process is asynchronous, it can return a promise to signal success or failure. The `reason` parameter contains a [`DOMString`](../domstring) describing why the stream was cancelled.

type <span class="badge inline optional">Optional</span>   
This property controls what type of readable stream is being dealt with. If it is included with a value set to `"bytes"`, the passed controller object will be a [`ReadableByteStreamController`](../readablebytestreamcontroller) capable of handling a BYOB (bring your own buffer)/byte stream. If it is not included, the passed controller will be a [`ReadableStreamDefaultController`](../readablestreamdefaultcontroller).

autoAllocateChunkSize <span class="badge inline optional">Optional</span>   
For byte streams, the developer can set the `autoAllocateChunkSize` with a positive integer value to turn on the stream's auto-allocation feature. With this turned on, the stream implementation will automatically allocate an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) with a size of the given integer, and the consumer can also use a default reader.

queuingStrategy <span class="badge inline optional">Optional</span>   
An object that optionally defines a queuing strategy for the stream. This takes two parameters:

highWaterMark  
A non-negative integer — this defines the total number of chunks that can be contained in the internal queue before backpressure is applied.

size(chunk)  
A method containing a parameter `chunk` — this indicates the size to use for each chunk, in bytes.

**Note**: You could define your own custom `queuingStrategy`, or use an instance of [`ByteLengthQueuingStrategy`](../bytelengthqueuingstrategy) or [`CountQueuingStrategy`](../countqueuingstrategy) for this object value. If no `queuingStrategy` is supplied, the default used is the same as a `CountQueuingStrategy` with a high water mark of 1.

### Return value

An instance of the [`ReadableStream`](../readablestream) object.

### Exceptions

RangeError  
The supplied type value is neither `"bytes"` nor `undefined`.

Examples
--------

In the following simple example, a custom `ReadableStream` is created using a constructor (see our [Simple random stream example](https://mdn.github.io/dom-examples/streams/simple-random-stream/) for the full code). The `start()` function generates a random string of text every second and enqueues it into the stream. A `cancel()` fuction is also provided to stop the generation if [`ReadableStream.cancel()`](cancel) is called for any reason.

When a button is pressed, the generation is stopped, the stream is closed using [`ReadableStreamDefaultController.close()`](../readablestreamdefaultcontroller/close), and another function is run, which reads the data back out of the stream.

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

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#rs-constructor">Streams<br />
<span class="small">The definition of 'ReadableStream()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

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

`ReadableStream`

43

79

65

No

30

10.1

43

43

65

30

10.3

4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ReadableStream/ReadableStream" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ReadableStream/ReadableStream</a>
