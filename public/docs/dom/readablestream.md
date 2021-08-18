ReadableStream
==============

The `ReadableStream` interface of the [Streams API](streams_api) represents a readable stream of byte data. The [Fetch API](fetch_api) offers a concrete instance of a `ReadableStream` through the [`body`](body/body) property of a [`Response`](response) object.

Constructor
-----------

[`ReadableStream()`](readablestream/readablestream)  
Creates and returns a readable stream object from the given handlers.

Properties
----------

 [`ReadableStream.locked`](readablestream/locked) <span class="badge inline readonly">Read only </span>   
The `locked` getter returns whether or not the readable stream is <a href="https://streams.spec.whatwg.org/#locked-to-a-reader" id="ref-for-locked-to-a-reader②">locked to a reader</a>.

Methods
-------

[`ReadableStream.cancel()`](readablestream/cancel)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves when the stream is canceled. Calling this method signals a loss of interest in the stream by a consumer. The supplied `reason` argument will be given to the underlying source, which may or may not use it.

[`ReadableStream.getReader()`](readablestream/getreader)  
Creates a reader and locks the stream to it. While the stream is locked, no other reader can be acquired until this one is released.

[`ReadableStream.pipeThrough()`](readablestream/pipethrough)  
Provides a chainable way of piping the current stream through a transform stream or any other writable/readable pair.

[`ReadableStream.pipeTo()`](readablestream/pipeto)  
Pipes the current ReadableStream to a given [`WritableStream`](writablestream) and returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that fulfills when the piping process completes successfully, or rejects if any errors were encountered.

[`ReadableStream.tee()`](readablestream/tee)  
The `tee` method <a href="https://streams.spec.whatwg.org/#tee-a-readable-stream" id="ref-for-tee-a-readable-stream②">tees</a> this readable stream, returning a two-element array containing the two resulting branches as new [`ReadableStream`](readablestream) instances. Each of those streams receives the same incoming data.

Examples
--------

### Fetch stream

In the following example, an artificial [`Response`](response) is created to stream HTML fragments fetched from another resource to the browser.

It demonstrates the usage of a [`ReadableStream`](readablestream) in combination with a [`Uint8Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint8Array).

    fetch('https://www.example.org')
    .then(response => response.body)
    .then(rb => {
      const reader = rb.getReader();

      return new ReadableStream({
        start(controller) {
          // The following function handles each data chunk
          function push() {
            // "done" is a Boolean and value a "Uint8Array"
            reader.read().then( ({done, value}) => {
              // If there is no more data to read
              if (done) {
                console.log('done', done);
                controller.close();
                return;
              }
              // Get the data and send it to the browser via the controller
              controller.enqueue(value);
              // Check chunks by logging to the console
              console.log(done, value);
              push();
            })
          }

          push();
        }
      });
    })
    .then(stream => {
      // Respond with our stream
      return new Response(stream, { headers: { "Content-Type": "text/html" } }).text();
    })
    .then(result => {
      // Do things with result
      console.log(result);
    });

### Async iterator to stream

Converting an [(async) iterator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Iterators_and_Generators) to a readable stream:

    function iteratorToStream(iterator) {
      return new ReadableStream({
        async pull(controller) {
          const { value, done } = await iterator.next();

          if (done) {
            controller.close();
          } else {
            controller.enqueue(value);
          }
        },
      });
    }

This works with both async and non-async iterators.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#rs-class">Streams<br />
<span class="small">The definition of 'ReadableStream' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

14

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

`cancel`

43

14

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

`getReader`

43

14

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

`locked`

43

14

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

`pipeThrough`

59

79

No

No

46

10.1

59

59

No

43

10.3

7.0

`pipeTo`

59

79

No

No

46

10.1

59

59

No

43

10.3

7.0

`tee`

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

See also
--------

-   [WHATWG Stream Visualiser](https://whatwg-stream-visualizer.glitch.me/), for a basic visualisation of readable, writable, and transform streams.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ReadableStream" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ReadableStream</a>
