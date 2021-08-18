# MediaStreamAudioDestinationNode

The `MediaStreamAudioDestinationNode` interface represents an audio destination consisting of a [WebRTC](webrtc_api) [`MediaStream`](mediastream) with a single `AudioMediaStreamTrack`, which can be used in a similar way to a `MediaStream` obtained from [`Navigator.getUserMedia()`](navigator/getusermedia).

It is an [`AudioNode`](audionode) that acts as an audio destination, created using the [`AudioContext.createMediaStreamDestination()`](audiocontext/createmediastreamdestination) method.

<table><tbody><tr class="odd"><td>Number of inputs</td><td><code>1</code></td></tr><tr class="even"><td>Number of outputs</td><td><code>0</code></td></tr><tr class="odd"><td>Channel count</td><td><code>2</code></td></tr><tr class="even"><td>Channel count mode</td><td><code>"explicit"</code></td></tr><tr class="odd"><td>Channel count interpretation</td><td><code>"speakers"</code></td></tr></tbody></table>

## Constructor

[`MediaStreamAudioDestinationNode.MediaStreamAudioDestinationNode()`](mediastreamaudiodestinationnode/mediastreamaudiodestinationnode)  
Creates a new `MediaStreamAudioDestinationNode` object instance.

## Properties

_Inherits properties from its parent, [`AudioNode`](audionode)_.

[`MediaStreamAudioDestinationNode.stream`](mediastreamaudiodestinationnode/stream)  
A [`MediaStream`](mediastream) containing a single [`MediaStreamTrack`](mediastreamtrack) whose [`kind`](mediastreamtrack/kind) is `audio` and with the same number of channels as the node. You can use this property to get a stream out of the audio graph and feed it into another construct, such as a [Media Recorder](mediastream_recording_api).

## Methods

_Inherits methods from its parent, [`AudioNode`](audionode)_.

## Example

In the following simple example, we create a [`MediaStreamAudioDestinationNode`](mediastreamaudiodestinationnode), an [`OscillatorNode`](oscillatornode) and a [`MediaRecorder`](mediarecorder) (the example will therefore only work in Firefox and Chrome at this time.) The `MediaRecorder` is set up to record information from the `MediaStreamDestinationNode`.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#mediastreamaudiodestinationnode">Web Audio API<br />
<span class="small">The definition of 'MediaStreamAudioDestinationNode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`MediaStreamAudioDestinationNode`

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

`MediaStreamAudioDestinationNode`

55

Before Chrome 59, the default values were not supported.

≤79

53

No

42

14.1

55

Before Chrome 59, the default values were not supported.

55

Before Chrome 59, the default values were not supported.

53

42

14.5

6.0

Before Samsung Internet 7.0, the default values were not supported.

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

- [Using the Web Audio API](web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamAudioDestinationNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamAudioDestinationNode</a>
