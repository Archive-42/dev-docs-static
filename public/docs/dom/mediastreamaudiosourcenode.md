MediaStreamAudioSourceNode
==========================

The `MediaStreamAudioSourceNode` interface is a type of [`AudioNode`](audionode) which operates as an audio source whose media is received from a [`MediaStream`](mediastream) obtained using the WebRTC or Media Capture and Streams APIs. This media could be from a microphone (through [`getUserMedia()`](mediadevices/getusermedia)) or from a remote peer on a WebRTC call (using the [`RTCPeerConnection`](rtcpeerconnection)'s audio tracks).

A `MediaStreamAudioSourceNode` has no inputs and exactly one output, and is created using the [`AudioContext.createMediaStreamSource()`](audiocontext/createmediastreamsource) method.

The `MediaStreamAudioSourceNode` takes the audio from the *first* [`MediaStreamTrack`](mediastreamtrack) whose [`kind`](mediastreamtrack/kind) attribute's value is `audio`. See [Track ordering](#track_ordering) for more information about the order of tracks.

The number of channels output by the node matches the number of tracks found in the selected audio track.

<table><tbody><tr class="odd"><td>Number of inputs</td><td><code>0</code></td></tr><tr class="even"><td>Number of outputs</td><td><code>1</code></td></tr><tr class="odd"><td>Channel count</td><td>defined by the first audio <a href="mediastreamtrack"><code>MediaStreamTrack</code></a> passed to the <a href="audiocontext/createmediastreamsource"><code>AudioContext.createMediaStreamSource()</code></a> method that created it.</td></tr></tbody></table>

Constructor
-----------

[`new MediaStreamAudioSourceNode()`](mediastreamaudiosourcenode/mediastreamaudiosourcenode)  
Creates a new `MediaStreamAudioSourceNode` object instance with the specified options.

Properties
----------

*In addition to the following properties, `MediaStreamAudioSourceNode` inherits the properties of its parent, [`AudioNode`](audionode).*

 [`mediaStream`](mediastreamaudiosourcenode/mediastream) <span class="badge inline readonly">Read only </span>   
The [`MediaStream`](mediastream) used when constructing this `MediaStreamAudioSourceNode`.

Methods
-------

*Inherits methods from its parent, [`AudioNode`](audionode)*.

Exceptions
----------

`InvalidStateError`  
The stream specified by the `mediaStream` parameter does not contain any audio tracks.

Usage notes
-----------

### Track ordering

For the purposes of the `MediaStreamTrackAudioSourceNode` interface, the order of the audio tracks on the stream is determined by taking the tracks whose [`kind`](mediastreamtrack/kind) is `audio`, then sorting the tracks by their [`id`](mediastreamtrack/id) property's values, in Unicode code point order (essentially, in alphabetical or lexicographical order, for IDs which are simple alphanumeric strings).

The **first** track, then, is the track whose `id` comes first when the tracks' IDs are all sorted by Unicode code point.

However, it's important to note that the rule establishing this ordering was added long after this interface was first introduced into the [Web Audio API](web_audio_api). As such, you can't easily rely on the order matching between any two browsers or browser versions.

The [`MediaStreamTrackAudioSourceNode`](mediastreamtrackaudiosourcenode) interface is similar to `MediaStreamAudioSourceNode`, but avoids this problem by letting you specify which track you want to use.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#mediastreamaudiosourcenode">Web Audio API<br />
<span class="small">The definition of 'MediaStreamAudioSourceNode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`MediaStreamAudioSourceNode`

23

12

25

No

15

11

≤37

Yes

25

14

11

Yes

`MediaStreamAudioSourceNode`

55

Before Chrome 59, the default values were not supported.

79

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

`mediaStream`

23

≤79

70

No

Yes

11

≤37

Yes

No

Yes

11

Yes

See also
--------

-   [Using the Web Audio API](web_audio_api/using_web_audio_api)
-   [WebRTC API](webrtc_api)
-   [Media Capture and Streams API (Media Streams)](media_streams_api)
-   [`MediaStreamTrackAudioSourceNode`](mediastreamtrackaudiosourcenode)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamAudioSourceNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamAudioSourceNode</a>
