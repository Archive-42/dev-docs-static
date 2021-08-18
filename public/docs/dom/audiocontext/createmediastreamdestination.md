# AudioContext.createMediaStreamDestination()

The `createMediaStreamDestination()` method of the [`AudioContext`](../audiocontext) Interface is used to create a new [`MediaStreamAudioDestinationNode`](../mediastreamaudiodestinationnode) object associated with a [WebRTC](../webrtc_api) [`MediaStream`](../mediastream) representing an audio stream, which may be stored in a local file or sent to another computer.

The [`MediaStream`](../mediastream) is created when the node is created and is accessible via the [`MediaStreamAudioDestinationNode`](../mediastreamaudiodestinationnode)'s `stream` attribute. This stream can be used in a similar way as a `MediaStream` obtained via [`navigator.getUserMedia`](../navigator/getusermedia) — it can, for example, be sent to a remote peer using the `RTCPeerConnection` `addStream()` method.

For more details about media stream destination nodes, check out the [`MediaStreamAudioDestinationNode`](../mediastreamaudiodestinationnode) reference page.

## Syntax

    var audioCtx = new AudioContext();
    var destination = audioCtx.createMediaStreamDestination();

### Returns

A [`MediaStreamAudioDestinationNode`](../mediastreamaudiodestinationnode).

## Examples

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audiocontext-createmediastreamdestination">Web Audio API<br />
<span class="small">The definition of 'createMediaStreamDestination()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`createMediaStreamDestination`

14

79

25

No

15

6

≤37

18

25

14

Yes

1.0

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioContext/createMediaStreamDestination" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioContext/createMediaStreamDestination</a>
