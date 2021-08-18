WritableStreamDefaultWriter.write()
===================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `write()` method of the [`WritableStreamDefaultWriter`](../writablestreamdefaultwriter) interface writes a passed chunk of data to a [`WritableStream`](../writablestream) and its underlying sink, then returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to indicate the success or failure of the write operation.

Note that what "success" means is up to the underlying sink; it might indicate that the chunk has been accepted, and not necessarily that it is safely saved to its ultimate destination.

Syntax
------

    var promise = writableStreamDefaultWriter.write(chunk);

### Parameters

chunk  
A block of binary data to pass to the `WritableStream`.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise), which fulfills with the `undefined` upon a successful write, or rejects if the write fails or stream becomes errored before the writing process is initiated.

### Exceptions

TypeError  
The target stream is not a writable stream, or it does not have an owner.

Examples
--------

The following example shows the creation of a `WritableStream` with a custom sink and an API-supplied queuing strategy. It then calls a function called `sendMessage()`, passing the newly created stream and a string. Inside this function it calls the stream's `getWriter()` method, which returns an instance of [`WritableStreamDefaultWriter`](../writablestreamdefaultwriter). A `forEach()` call is used to write each chunk of the string to the stream. Finally, `write()` and `close()` return promises that are processed to deal with success or failure of chunks and streams.

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

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#default-writer-write">Streams<br />
<span class="small">The definition of 'write()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`write`

59

16

No

No

46

14.1

59

59

No

43

14.5

7.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WritableStreamDefaultWriter/write" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WritableStreamDefaultWriter/write</a>
