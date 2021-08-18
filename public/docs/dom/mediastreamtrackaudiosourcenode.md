MediaStreamTrackAudioSourceNode
===============================

The `MediaStreamTrackAudioSourceNode` interface is a type of [`AudioNode`](audionode) which represents a source of audio data taken from a specific [`MediaStreamTrack`](mediastreamtrack) obtained through the [WebRTC](webrtc_api) or [Media Capture and Streams](media_streams_api) APIs. The audio itself might be input from a microphone or other audio sampling device, or might be received through a [`RTCPeerConnection`](rtcpeerconnection), among other posible options.

A `MediaStreamTrackAudioSourceNode` has no inputs and exactly one output, and is created using the [`AudioContext.createMediaStreamTrackSource()`](audiocontext/createmediastreamtracksource) method. This interface is similar to [`MediaStreamAudioSourceNode`](mediastreamaudiosourcenode), except it lets you specifically state the track to use, rather than assuming the first audio track on a stream.

<table><tbody><tr class="odd"><td>Number of inputs</td><td><code>0</code></td></tr><tr class="even"><td>Number of outputs</td><td><code>1</code></td></tr><tr class="odd"><td>Channel count</td><td>defined by the first audio <a href="mediastreamtrack"><code>MediaStreamTrack</code></a> passed to the <a href="audiocontext/createmediastreamtracksource"><code>AudioContext.createMediaStreamTrackSource()</code></a> method that created it.</td></tr></tbody></table>

Constructor
-----------

[`new MediaStreamTrackAudioSourceNode()`](mediastreamtrackaudiosourcenode/mediastreamtrackaudiosourcenode)  
Creates a new `MediaStreamTrackAudioSourceNode` object instance with the specified options.

Properties
----------

*The `MediaStreamTrackAudioSourceNode` interface has no properties of its own; however, it inherits the properties of its parent, [`AudioNode`](audionode).*

Methods
-------

*Inherits methods from its parent, [`AudioNode`](audionode)*.

Example
-------

In this example, we grab a media (audio + video) stream from [`navigator.getUserMedia`](navigator/getusermedia), feed the media into a [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element to play then mute the audio, but then also feed the audio into a [`MediaStreamAudioSourceNode`](mediastreamaudiosourcenode). Next, we feed this source audio into a low pass [`BiquadFilterNode`](biquadfilternode) (which effectively serves as a bass booster), then a [`AudioDestinationNode`](audiodestinationnode).

The range slider below the [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element controls the amount of gain given to the lowpass filter — increase the value of the slider to make the audio sound more bass heavy!

**Note**: You can see this [example running live](https://mdn.github.io/webaudio-examples/stream-source-buffer/), or [view the source](https://github.com/mdn/webaudio-examples/tree/master/stream-source-buffer).

    var pre = document.querySelector('pre');
    var video = document.querySelector('video');
    var myScript = document.querySelector('script');
    var range = document.querySelector('input');

    // getUserMedia block - grab stream
    // put it into a MediaStreamAudioSourceNode
    // also output the visuals into a video element

    if (navigator.mediaDevices) {
        console.log('getUserMedia supported.');
        navigator.mediaDevices.getUserMedia ({audio: true, video: true})
        .then(function(stream) {
            video.srcObject = stream;
            video.onloadedmetadata = function(e) {
                video.play();
                video.muted = true;
            };

            // Create a MediaStreamAudioSourceNode
            // Feed the HTMLMediaElement into it
            var audioCtx = new AudioContext();
            var source = audioCtx.createMediaStreamSource(stream);

            // Create a biquadfilter
            var biquadFilter = audioCtx.createBiquadFilter();
            biquadFilter.type = "lowshelf";
            biquadFilter.frequency.value = 1000;
            biquadFilter.gain.value = range.value;

            // connect the AudioBufferSourceNode to the gainNode
            // and the gainNode to the destination, so we can play the
            // music and adjust the volume using the mouse cursor
            source.connect(biquadFilter);
            biquadFilter.connect(audioCtx.destination);

            // Get new mouse pointer coordinates when mouse is moved
            // then set new gain value

            range.oninput = function() {
                biquadFilter.gain.value = range.value;
            }
        })
        .catch(function(err) {
            console.log('The following gUM error occurred: ' + err);
        });
    } else {
       console.log('getUserMedia not supported on your browser!');
    }

    // dump script to pre element

    pre.innerHTML = myScript.innerHTML;

**Note**: As a consequence of calling `createMediaStreamSource()`, audio playback from the media stream will be re-routed into the processing graph of the [`AudioContext`](audiocontext). So playing/pausing the stream can still be done through the media element API and the player controls.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#mediastreamtrackaudiosourcenode">Web Audio API<br />
<span class="small">The definition of 'MediaStreamTrackAudioSourceNode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`MediaStreamTrackAudioSourceNode`

No

No

68

No

No

No

No

No

68

No

No

No

`MediaStreamTrackAudioSourceNode`

No

No

68

Firefox 68 implements the updated standard's definition of the "first" audio track; now the first track is the one whose ID comes first lexicographically.

No

No

No

No

No

68

Firefox 68 implements the updated standard's definition of the "first" audio track; now the first track is the one whose ID comes first lexicographically.

No

No

No

`mediaStreamTrack`

No

No

68

No

No

No

No

No

68

No

No

No

See also
--------

-   [Using the Web Audio API](web_audio_api/using_web_audio_api)
-   [WebRTC API](webrtc_api)
-   [Media Capture and Streams API (Media Streams)](media_streams_api)
-   [`MediaStreamAudioSourceNode`](mediastreamaudiosourcenode)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrackAudioSourceNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrackAudioSourceNode</a>
