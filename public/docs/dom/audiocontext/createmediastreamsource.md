# AudioContext.createMediaStreamSource()

The `createMediaStreamSource()` method of the [`AudioContext`](../audiocontext) Interface is used to create a new [`MediaStreamAudioSourceNode`](../mediastreamaudiosourcenode) object, given a media stream (say, from a [`MediaDevices.getUserMedia`](../mediadevices/getusermedia) instance), the audio from which can then be played and manipulated.

For more details about media stream audio source nodes, check out the [`MediaStreamAudioSourceNode`](../mediastreamaudiosourcenode) reference page.

## Syntax

    audioSourceNode = audioContext.createMediaStreamSource(stream);

### Parameters

`stream`  
A [`MediaStream`](../mediastream) to serve as an audio source to be fed into an audio processing graph for use and manipulation.

### Return value

A new [`MediaStreamAudioSourceNode`](../mediastreamaudiosourcenode) object representing the audio node whose media is obtained from the specified source stream.

## Example

In this example, we grab a media (audio + video) stream from [`navigator.getUserMedia`](../navigator/getusermedia), feed the media into a [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element to play then mute the audio, but then also feed the audio into a [`MediaStreamAudioSourceNode`](../mediastreamaudiosourcenode). Next, we feed this source audio into a low pass [`BiquadFilterNode`](../biquadfilternode) (which effectively serves as a bass booster), then a [`AudioDestinationNode`](../audiodestinationnode).

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

**Note**: As a consequence of calling `createMediaStreamSource()`, audio playback from the media stream will be re-routed into the processing graph of the [`AudioContext`](../audiocontext). So playing/pausing the stream can still be done through the media element API and the player controls.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audiocontext-createmediastreamsource">Web Audio API<br />
<span class="small">The definition of 'AudioContext.createMediaStreamSource()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`createMediaStreamSource`

14

12

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioContext/createMediaStreamSource" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioContext/createMediaStreamSource</a>
