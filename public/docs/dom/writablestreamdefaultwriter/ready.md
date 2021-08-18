WritableStreamDefaultWriter.ready
=================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `ready` read-only property of the [`WritableStreamDefaultWriter`](../writablestreamdefaultwriter) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves when the desired size of the stream's internal queue transitions from non-positive to positive, signaling that it is no longer applying backpressure.

Syntax
------

    var promise = writableStreamDefaultWriter.ready;

### Value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise).

Example
-------

The following example shows two uses of the `ready` property. The first uses `ready` to ensure that the `WritableStream` is done writing and thus able to receive data before sending a binary chunk. The second also checks whether the the `WritableStream` is done writing, but this time because the writing must be finished before the writer can be closed.

    function sendMessage(message, writableStream) {
      // defaultWriter is of type WritableStreamDefaultWriter
      var defaultWriter = writableStream.getWriter();
      var encoder = new TextEncoder();
      var encoded = encoder.encode(message, {stream: true});
      encoded.forEach(function(chunk) {
        // Make sure the stream and its writer are able to
        //   receive data.
        defaultWriter.ready
        .then(function() {
          defaultWriter.write(chunk)
          .then(function() {
            console.log("Chunk written to sink.);
          })
          .catch(function(err) {
            console.log("Chunk error: " + err);
          });
        });
        // Call ready again to ensure that all chunks are written
        //   before closing the writer.
        defaultWriter.ready
        .then(function() {
          defaultWriter.close()
          .then(function() {
            console.log("All chunks written");
          })
          .catch(function(err) {
            console.log("Stream error: " + err);
          });
        });
      });
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#default-writer-ready">Streams<br />
<span class="small">The definition of 'ready' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WritableStreamDefaultWriter/ready" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WritableStreamDefaultWriter/ready</a>
