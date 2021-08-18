WritableStreamDefaultWriter
===========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `WritableStreamDefaultWriter` interface of the [Streams API](streams_api) is the object returned by [`WritableStream.getWriter()`](writablestream/getwriter) and once created locks the writer to the `WritableStream` ensuring that no other streams can write to the underlying sink.

Constructor
-----------

[`WritableStreamDefaultWriter()`](writablestreamdefaultwriter/writablestreamdefaultwriter)  
Creates a new `WritableStreamDefaultWriter` object instance.

Properties
----------

 [`WritableStreamDefaultWriter.closed`](writablestreamdefaultwriter/closed)<span class="badge inline readonly">Read only </span>   
Allows you to write code that responds to an end to the streaming process. Returns a promise that fulfills if the stream becomes closed or the writer's lock is released, or rejects if the stream errors.

 [`WritableStreamDefaultWriter.desiredSize`](writablestreamdefaultwriter/desiredsize)<span class="badge inline readonly">Read only </span>   
Returns the desired size required to fill the stream's internal queue.

 [`WritableStreamDefaultWriter.ready`](writablestreamdefaultwriter/ready)<span class="badge inline readonly">Read only </span>   
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves when the desired size of the stream's internal queue transitions from non-positive to positive, signaling that it is no longer applying backpressure.

Methods
-------

[`WritableStreamDefaultWriter.abort()`](writablestreamdefaultwriter/abort)  
Aborts the stream, signaling that the producer can no longer successfully write to the stream and it is to be immediately moved to an error state, with any queued writes discarded.

[`WritableStreamDefaultWriter.close()`](writablestreamdefaultwriter/close)  
Closes the associated writable stream.

[`WritableStreamDefaultWriter.releaseLock()`](writablestreamdefaultwriter/releaselock)  
Releases the writer's lock on the corresponding stream. After the lock is released, the writer is no longer active. If the associated stream is errored when the lock is released, the writer will appear errored in the same way from now on; otherwise, the writer will appear closed.

[`WritableStreamDefaultWriter.write()`](writablestreamdefaultwriter/write)  
Writes a passed chunk of data to a [`WritableStream`](writablestream) and its underlying sink, then returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to indicate the success or failure of the write operation.

Examples
--------

The following example shows the creation of a `WritableStream` with a custom sink and an API-supplied queuing strategy. It then calls a function called `sendMessage()`, passing the newly created stream and a string. Inside this function it calls the stream's `getWriter()` method, which returns an instance of [`WritableStreamDefaultWriter`](writablestreamdefaultwriter). A `forEach()` call is used to write each chunk of the string to the stream. Finally, `write()` and `close()` return promises that are processed to deal with success or failure of chunks and streams.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#default-writer-class">Streams<br />
<span class="small">The definition of 'WritableStreamDefaultWriter' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`WritableStreamDefaultWriter`

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

`WritableStreamDefaultWriter`

59

16

No

No

46

No

59

59

No

43

No

7.0

`abort`

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

`close`

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

`closed`

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

`desiredSize`

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

`ready`

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

`releaseLock`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WritableStreamDefaultWriter" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WritableStreamDefaultWriter</a>
