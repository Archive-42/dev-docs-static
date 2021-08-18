# Body.arrayBuffer()

The `arrayBuffer()` method of the [`Body`](../body) mixin takes a [`Response`](../response) stream and reads it to completion. It returns a promise that resolves with an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer).

## Syntax

    response.arrayBuffer().then(function(buffer) {
      // do something with buffer
    });

### Parameters

None.

### Return value

A promise that resolves with an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer).

## Examples

### Playing music

In our [fetch array buffer live](https://mdn.github.io/fetch-examples/fetch-array-buffer/), we have a Play button. When pressed, the `getData()` function is run. Note that before playing full audio file will be downloaded. If you need to play ogg during downloading (stream it) - consider [`HTMLAudioElement`](../htmlaudioelement):

    new Audio("music.ogg").play();

In `getData()` we create a new request using the [`Request()`](../request/request) constructor, then use it to fetch an OGG music track. We also use [`AudioContext.createBufferSource`](../baseaudiocontext/createbuffersource) to create an audio buffer source. When the fetch is successful, we read an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) out of the response using `arrayBuffer()`, decode the audio data using [`AudioContext.decodeAudioData()`](../baseaudiocontext/decodeaudiodata), set the decoded data as the audio buffer source's buffer (`source.buffer`), then connect the source up to the [`AudioContext.destination`](../baseaudiocontext/destination).

Once `getData()` has finished running, we start the audio source playing with `start(0)`, then disable the play button so it can't be clicked again when it is already playing (this would cause an error.)

    function getData() {
      source = audioCtx.createBufferSource();

      var myRequest = new Request('viper.ogg');

      fetch(myRequest).then(function(response) {
        return response.arrayBuffer();
      }).then(function(buffer) {
        audioCtx.decodeAudioData(buffer, function(decodedData) {
          source.buffer = decodedData;
          source.connect(audioCtx.destination);
        });
      });
    };

    // wire up buttons to stop and play audio

    play.onclick = function() {
      getData();
      source.start(0);
      play.setAttribute('disabled', 'disabled');
    }

### Reading files

The [`Response()`](../response/response) constructor accepts [`File`](../file)s and [`Blob`](../blob)s, so it may be used to read a [`File`](../file) into other formats.

    function readFile(file) {
      return new Response(file).arrayBuffer();
    }

    <input type="file" onchange="readFile(this.files[0])">

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#dom-body-arraybuffer">Fetch<br />
<span class="small">The definition of 'arrayBuffer()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`arrayBuffer`

42

≤18

39

No

29

10.1

No

42

No

29

10.3

4.0

## See also

- [ServiceWorker API](../service_worker_api)
- [HTTP access control (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
- [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Body/arrayBuffer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Body/arrayBuffer</a>
