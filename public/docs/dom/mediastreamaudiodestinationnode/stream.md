# MediaStreamAudioDestinationNode.stream

The `stream` property of the [`AudioContext`](../audiocontext) interface represents a [`MediaStream`](../mediastream) containing a single audio [`MediaStreamTrack`](../mediastreamtrack) with the same number of channels as the node itself.

You can use this property to get a stream out of the audio graph and feed it into another construct, such as a [Media Recorder](../mediastream_recording_api).

## Syntax

    var audioCtx = new AudioContext();
    var destination = audioCtx.createMediaStreamDestination();
    var myStream = destination.stream;

### Value

A [`MediaStream`](../mediastream) containing a single audio track. The audio track is a [`MediaStreamTrack`](../mediastreamtrack) whose [`kind`](../mediastreamtrack/kind) is `audio`.

## Example

In the following simple example, we create a [`MediaStreamAudioDestinationNode`](../mediastreamaudiodestinationnode), an [`OscillatorNode`](../oscillatornode) and a [`MediaRecorder`](../mediarecorder) (the example will therefore only work in Firefox and Chrome at this time.) The `MediaRecorder` is set up to record information from the `MediaStreamDestinationNode`.

When the button is clicked, the oscillator starts, and the `MediaRecorder` is started. When the button is stopped, the oscillator and` MediaRecorder` both stop. Stopping the `MediaRecorder` causes the `dataavailable` event to fire, and the event data is pushed into the `chunks` array. After that, the `stop` event fires, a new `blob` is made of type opus — which contains the data in the `chunks` array, and a new window (tab) is then opened that points to a URL created from the blob.

From here, you can play and save the opus file.

    <!DOCTYPE html>
    <html>
      <head>
        <title>createMediaStreamDestination() demo</title>
      </head>
      <body>
        <h1>createMediaStreamDestination() demo</h1>

        <p>Encoding a pure sine wave to an Opus file </p>
        <button>Make sine wave</button>
        <audio controls></audio>
        <script>
         var b = document.querySelector("button");
         var clicked = false;
         var chunks = [];
         var ac = new AudioContext();
         var osc = ac.createOscillator();
         var dest = ac.createMediaStreamDestination();
         var mediaRecorder = new MediaRecorder(dest.stream);
         osc.connect(dest);

         b.addEventListener("click", function(e) {
           if (!clicked) {
               mediaRecorder.start();
               osc.start(0);
               e.target.textContent = "Stop recording";
               clicked = true;
             } else {
               mediaRecorder.stop();
               osc.stop(0);
               e.target.disabled = true;
             }
         });

         mediaRecorder.ondataavailable = function(evt) {
           // push each chunk (blobs) in an array
           chunks.push(evt.data);
         };

         mediaRecorder.onstop = function(evt) {
           // Make blob out of our blobs, and open it.
           var blob = new Blob(chunks, { 'type' : 'audio/ogg; codecs=opus' });
           document.querySelector("audio").src = URL.createObjectURL(blob);
         };
        </script>
      </body>
    </html>

**Note**: You can [view this example live](https://mdn.github.io/webaudio-examples/create-media-stream-destination/index.html), or [study the source code](https://github.com/mdn/webaudio-examples/blob/master/create-media-stream-destination/index.html), on Github.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-mediastreamaudiodestinationnode-stream">Web Audio API<br />
<span class="small">The definition of 'stream' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`stream`

14

≤18

25

No

15

6

≤37

18

25

14

6

1.0

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamAudioDestinationNode/stream" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamAudioDestinationNode/stream</a>
