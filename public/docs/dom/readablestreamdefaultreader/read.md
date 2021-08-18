# ReadableStreamDefaultReader.read()

The `read()` method of the [`ReadableStreamDefaultReader`](../readablestreamdefaultreader) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) providing access to the next chunk in the stream's internal queue.

## Syntax

    var promise = readableStreamDefaultReader.read();

### Parameters

None.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise), which fulfills/rejects with a result depending on the state of the stream. The different possibilities are as follows:

- If a chunk is available, the promise will be fulfilled with an object of the form `{ value: theChunk, done: false }`.
- If the stream becomes closed, the promise will be fulfilled with an object of the form `{ value: undefined, done: true }`.
- If the stream becomes errored, the promise will be rejected with the relevant error.

### Exceptions

TypeError  
The source object is not a `ReadableStreamDefaultReader`, or the stream has no owner.

## Examples

### Example 1 - simple example

This example shows the basic API usage, but doesn't try to deal with complications like stream chunks not ending on line boundaries for example.

In this example `stream` is a previously-created custom `ReadableStream`. It is read using a [`ReadableStreamDefaultReader`](../readablestreamdefaultreader) created using `getReader()`. (see our [Simple random stream example](https://mdn.github.io/dom-examples/streams/simple-random-stream/) for the full code). Each chunk is read sequentially and output to the UI as an array of UTF-8 bytes, until the stream has finished being read, at which point we return out of the recursive function and print the entire stream to another part of the UI.

    function fetchStream() {
      const reader = stream.getReader();
      let charsReceived = 0;

      // read() returns a promise that resolves
      // when a value has been received
      reader.read().then(function processText({ done, value }) {
        // Result objects contain two properties:
        // done  - true if the stream has already given you all its data.
        // value - some data. Always undefined when done is true.
        if (done) {
          console.log("Stream complete");
          para.textContent = result;
          return;
        }

        // value for fetch streams is a Uint8Array
        charsReceived += value.length;
        const chunk = value;
        let listItem = document.createElement('li');
        listItem.textContent = 'Received ' + charsReceived + ' characters so far. Current chunk = ' + chunk;
        list2.appendChild(listItem);

        result += chunk;

        // Read some more, and call this function again
        return reader.read().then(processText);
      });
    }

### Example 2 - handling text line by line

This example shows how you might fetch a text file and handle it as a stream of text lines. It deals with stream chunks not ending on line boundaries and converting from Uint8Array to strings.

    async function* makeTextFileLineIterator(fileURL) {
      const utf8Decoder = new TextDecoder("utf-8");
      let response = await fetch(fileURL);
      let reader = response.body.getReader();
      let {value: chunk, done: readerDone} = await reader.read();
      chunk = chunk ? utf8Decoder.decode(chunk, {stream: true}) : "";

      let re = /\r\n|\n|\r/gm;
      let startIndex = 0;
      let result;

      for (;;) {
        let result = re.exec(chunk);
        if (!result) {
          if (readerDone) {
            break;
          }
          let remainder = chunk.substr(startIndex);
          ({value: chunk, done: readerDone} = await reader.read());
          chunk = remainder + (chunk ? utf8Decoder.decode(chunk, {stream: true}) : "");
          startIndex = re.lastIndex = 0;
          continue;
        }
        yield chunk.substring(startIndex, result.index);
        startIndex = re.lastIndex;
      }
      if (startIndex < chunk.length) {
        // last line didn't end in a newline char
        yield chunk.substr(startIndex);
      }
    }

    for await (let line of makeTextFileLineIterator(urlOfFile)) {
      processLine(line);
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#default-reader-read">Streams<br />
<span class="small">The definition of 'read()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`read`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ReadableStreamDefaultReader/read" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ReadableStreamDefaultReader/read</a>
