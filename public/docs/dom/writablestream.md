WritableStream
==============

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `WritableStream` interface of the [Streams API](streams_api) provides a standard abstraction for writing streaming data to a destination, known as a sink. This object comes with built-in backpressure and queuing.

Constructor
-----------

[`WritableStream()`](writablestream/writablestream)  
Creates a new `WritableStream` object.

Properties
----------

 [`WritableStream.locked`](writablestream/locked) <span class="badge inline readonly">Read only </span>   
A boolean indicating whether the `WritableStream` is locked to a writer.

Methods
-------

[`WritableStream.abort()`](writablestream/abort)  
Aborts the stream, signaling that the producer can no longer successfully write to the stream and it is to be immediately moved to an error state, with any queued writes discarded.

<span class="page-not-created">`WritableStream.close()`</span>  
Closes the stream.

[`WritableStream.getWriter()`](writablestream/getwriter)  
Returns a new instance of [`WritableStreamDefaultWriter`](writablestreamdefaultwriter) and locks the stream to that instance. While the stream is locked, no other writer can be acquired until this one is released.

Examples
--------

The following example illustrates several features of this interface. It shows the creation of the `WritableStream` with a custom sink and an API-supplied queueing strategy. It then calls a function called `sendMessage()`, passing the newly created stream and a string. Inside this function it calls the stream's `getWriter()` method, which returns an instance of [`WritableStreamDefaultWriter`](writablestreamdefaultwriter). A `forEach()` call is used to write each chunk of the string to the stream. Finally, `write()` and `close()` return promises that are processed to deal with success or failure of chunks and streams.

    const list = document.querySelector('ul');

    function sendMessage(message, writableStream) {
      // defaultWriter is of type WritableStreamDefaultWriter
      const defaultWriter = writableStream.getWriter();
      const encoder = new TextEncoder();
      const encoded = encoder.encode(message, { stream: true });
      encoded.forEach((chunk) => {
        defaultWriter.ready
          .then(() => {
            return defaultWriter.write(chunk);
          })
          .then(() => {
            console.log("Chunk written to sink.");
          })
          .catch((err) => {
            console.log("Chunk error:", err);
          });
      });
      // Call ready again to ensure that all chunks are written
      //   before closing the writer.
      defaultWriter.ready
        .then(() => {
          defaultWriter.close();
        })
        .then(() => {
          console.log("All chunks written");
        })
        .catch((err) => {
          console.log("Stream error:", err);
        });
    }

    const decoder = new TextDecoder("utf-8");
    const queuingStrategy = new CountQueuingStrategy({ highWaterMark: 1 });
    let result = "";
    const writableStream = new WritableStream({
      // Implement the sink
      write(chunk) {
        return new Promise((resolve, reject) => {
          var buffer = new ArrayBuffer(2);
          var view = new Uint16Array(buffer);
          view[0] = chunk;
          var decoded = decoder.decode(view, { stream: true });
          var listItem = document.createElement('li');
          listItem.textContent = "Chunk decoded: " + decoded;
          list.appendChild(listItem);
          result += decoded;
          resolve();
        });
      },
      close() {
        var listItem = document.createElement('li');
        listItem.textContent = "[MESSAGE RECEIVED] " + result;
        list.appendChild(listItem);
      },
      abort(err) {
        console.log("Sink error:", err);
      }
    }, queuingStrategy);

    sendMessage("Hello, world.", writableStream);

You can find the full code in our [Simple writer example](https://mdn.github.io/dom-examples/streams/simple-writer/).

### Backpressure

Because of how backpressure is supported in the API, its implementation in code may be less than obvious. To see how backpressure is implemented look for three things.

-   The `highWaterMark` property, which is set when creating the counting strategy (line 35), sets the maximum amount of data that the `WritableStream` instance will handle in a single `write()` operation. In this example, it's the maximum amount of data that can be sent to `defaultWriter.write()` (line 11).
-   The `defaultWriter.ready` property returns a promise that resolves when the sink (the first property of the `WritableStream` constructor) is done writing data. The data source can either write more data (line 9) or call `close()` (line 24). Calling close() too early can prevent data from being written. This is why the example calls `defaultWriter.ready` twice (lines 9 and 22).
-   The [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) returned by the sink's `write()` method (line 40) tells the `WritableStream` and its writer when to resolve `defaultWriter.ready`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#ws-class">Streams<br />
<span class="small">The definition of 'WritableStream' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`WritableStream`

59

16

No

No

47

14.1

59

59

No

44

14.5

7.0

`WritableStream`

59

16

No

No

47

14.1

59

59

No

44

14.5

7.0

`abort`

59

16

No

No

47

14.1

59

59

No

44

14.5

7.0

`close`

81

81

No

No

68

14.1

81

81

No

58

14.5

13.0

`getWriter`

59

16

No

No

47

14.1

59

59

No

44

14.5

7.0

`locked`

59

16

No

No

47

14.1

59

59

No

44

14.5

7.0

See also
--------

-   [WHATWG Stream Visualiser](https://whatwg-stream-visualizer.glitch.me/), for a basic visualisation of readable, writable, and transform streams.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WritableStream" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WritableStream</a>
