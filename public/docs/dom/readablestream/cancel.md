ReadableStream.cancel()
=======================

The `cancel()` method of the [`ReadableStream`](../readablestream) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves when the stream is canceled.

Cancel is used when you've completely finished with the stream and don't need any more data from it, even if there are chunks enqueued waiting to be read. That data is lost after cancel is called, and the stream is not readable any more. To read those chunks still and not completely get rid of the stream, you'd use [`ReadableStreamDefaultController.close()`](../readablestreamdefaultcontroller/close).

Syntax
------

    var promise = readableStream.cancel(reason);

### Parameters

reason <span class="badge inline optional">Optional</span>   
A human-readable reason for the cancellation. The underlying source may or may not use it.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise), which fulfills with the value given in the `reason` parameter.

### Exceptions

TypeError  
The stream you are trying to cancel is not a [`ReadableStream`](../readablestream), or it is locked.

Examples
--------

In Jake Archibald's [cancelling a fetch](https://jsbin.com/gameboy/edit?js,console) example, a stream is used to fetch the WHATWG HTML spec chunk by chunk; each chunk is searched for the string "service workers". When the search terms is found, `cancel()` is used to cancel the stream — the job is finished so it is no longer needed.

    var searchTerm = "service workers";
    // Chars to show either side of the result in the match
    var contextBefore = 30;
    var contextAfter = 30;
    var caseInsensitive = true;
    var url = 'https://html.spec.whatwg.org/';

    console.log(`Searching '${url}' for '${searchTerm}'`);

    fetch(url).then(response => {
      console.log('Received headers');

      var decoder = new TextDecoder();
      var reader = response.body.getReader();
      var toMatch = caseInsensitive ? searchTerm.toLowerCase() : searchTerm;
      var bufferSize = Math.max(toMatch.length - 1, contextBefore);

      var bytesReceived = 0;
      var buffer = '';
      var matchFoundAt = -1;

      return reader.read().then(function process(result) {
        if (result.done) {
          console.log('Failed to find match');
          return;
        }

        bytesReceived += result.value.length;
        console.log(`Received ${bytesReceived} bytes of data so far`);

        buffer += decoder.decode(result.value, {stream: true});

        // already found match & just context-gathering?
        if (matchFoundAt === -1) {
          matchFoundAt = (caseInsensitive ? buffer.toLowerCase() : buffer).indexOf(toMatch);
        }

        if (matchFoundAt === -1) {
          buffer = buffer.slice(-bufferSize);
        }
        else if (buffer.slice(matchFoundAt + toMatch.length).length >= contextAfter) {
          console.log("Here's the match:")
          console.log(buffer.slice(
            Math.max(0, matchFoundAt - contextBefore),
            matchFoundAt + toMatch.length + contextAfter
          ));
          console.log("Cancelling fetch");
          reader.cancel();
          return;
        }
        else {
          console.log('Found match, but need more context…');
        }

        // keep reading
        return reader.read().then(process);
      });
    }).catch(err => {
      console.log("Something went wrong. See devtools for details. Does the response lack CORS headers?");
      throw err;
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#rs-cancel">Streams<br />
<span class="small">The definition of 'cancel()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ReadableStream/cancel" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ReadableStream/cancel</a>
