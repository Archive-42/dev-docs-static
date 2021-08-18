WritableStream.WritableStream()
===============================

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `WritableStream()` constructor creates a new [`WritableStream`](../writablestream) object instance.

Syntax
------

    var writableStream = new WritableStream(underlyingSink[, queuingStrategy]);

### Parameters

underlyingSink <span class="badge inline optional">Optional</span>   
An object containing methods and properties that define how the constructed stream instance will behave. `underlyingSink` can contain the following:

start(controller) <span class="badge inline optional">Optional</span>   
This is a method, called immediately when the object is constructed. The contents of this method are defined by the developer, and should aim to get access to the underlying sink. If this process is to be done asynchronously, it can return a promise to signal success or failure. The `controller` parameter passed to this method is a [`WritableStreamDefaultController`](../writablestreamdefaultcontroller). This can be used by the developer to control the stream during set up.

write(chunk, controller) <span class="badge inline optional">Optional</span>   
This method, also defined by the developer, will be called when a new chunk of data (specified in the `chunk` parameter) is ready to be written to the underlying sink. It can return a promise to signal success or failure of the write operation. The `controller` parameter passed to this method is a [`WritableStreamDefaultController`](../writablestreamdefaultcontroller) that can be used by the developer to control the stream as more chunks are submitted for writing. This method will be called only after previous writes have succeeded, and never after the stream is closed or aborted (see below).

close(controller) <span class="badge inline optional">Optional</span>   
This method, also defined by the developer, will be called if the app signals that it has finished writing chunks to the stream. The contents should do whatever is necessary to finalize writes to the underlying sink, and release access to it. If this process is asynchronous, it can return a promise to signal success or failure. This method will be called only after all queued-up writes have succeeded. The `controller` parameter passed to this method is a [`WritableStreamDefaultController`](../writablestreamdefaultcontroller), which can be used to control the stream at the end of writing.

abort(reason) <span class="badge inline optional">Optional</span>   
This method, also defined by the developer, will be called if the app signals that it wishes to abruptly close the stream and put it in an errored state. It can clean up any held resources, much like `close()`, but `abort()` will be called even if writes are queued up — those chunks will be thrown away. If this process is asynchronous, it can return a promise to signal success or failure. The `reason` parameter contains a [`DOMString`](../domstring) describing why the stream was aborted.

queuingStrategy <span class="badge inline optional">Optional</span>   
An object that optionally defines a queuing strategy for the stream. This takes two parameters:

highWaterMark  
A non-negative integer — this defines the total number of chunks that can be contained in the internal queue before backpressure is applied.

size(chunk)  
A method containing a parameter `chunk` — this indicates the size to use for each chunk, in bytes.

**Note**: You could define your own custom `queuingStrategy`, or use an instance of [`ByteLengthQueuingStrategy`](../bytelengthqueuingstrategy) or [`CountQueuingStrategy`](../countqueuingstrategy) for this object value. If no `queuingStrategy` is supplied, the default used is the same as a `CountQueuingStrategy` with a high water mark of 1.

### Return value

An instance of the [`WritableStream`](../writablestream) object.

Examples
--------

The following example illustrates several features of this interface. It shows the creation of the `WritableStream` with a custom sink and an API-supplied queuing strategy. It then calls a function called `sendMessage()`, passing the newly created stream and a string. Inside this function it calls the stream's `getWriter()` method, which returns an instance of [`WritableStreamDefaultWriter`](../writablestreamdefaultwriter). A `forEach()` call is used to write each chunk of the string to the stream. Finally, `write()` and `close()` return promises that are processed to deal with success or failure of chunks and streams.

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
-   The `defaultWriter.ready` property returns a promise that resolves when the sink (the first property of the `WritableStream` constructor) is done writing data. The data source can wither write more data (line 11) or call `close()` (line 24). Calling `close()` too early can prevent data from being written. This is why the example calls `defaultWriter.ready` twice (lines 9 and 22).
-   The [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) returned by the sink's `write()` method (line 40) tells the `WritableStream` and its writer when to resolve `defaultWriter.ready`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#ws-constructor">Streams<br />
<span class="small">The definition of 'WritableStream()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WritableStream/WritableStream" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WritableStream/WritableStream</a>
