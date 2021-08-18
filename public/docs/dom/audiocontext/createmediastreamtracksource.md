# AudioContext.createMediaStreamTrackSource()

**Draft**

This page is not complete.

The `createMediaStreamTrackSource()` method of the [`AudioContext`](../audiocontext) interface creates and returns a [`MediaStreamTrackAudioSourceNode`](../mediastreamtrackaudiosourcenode) which represents an audio source whose data comes from the specified [`MediaStreamTrack`](../mediastreamtrack).

This differs from [`createMediaStreamSource()`](createmediastreamsource), which creates a [`MediaStreamAudioSourceNode`](../mediastreamaudiosourcenode) whose audio comes from the audio track in a specified [`MediaStream`](../mediastream) whose [`id`](../mediastreamtrack/id) is first, lexicographically (alphabetically).

## Syntax

    var audioCtx = new AudioContext();
    var track = audioCtx.createMediaStreamTrackSource(track);

### Parameters

`track`  
The [`MediaStreamTrack`](../mediastreamtrack) to use as the source of all audio data for the new node.

### Return value

A [`MediaStreamTrackAudioSourceNode`](../mediastreamtrackaudiosourcenode) object which acts as a source for audio data found in the specified audio track.

## Example

In this example, [`getUserMedia()`](../mediadevices/getusermedia) is used to request access to the user's microphone. Once that access is attained, an audio context is established and a [`MediaStreamTrackAudioSourceNode`](../mediastreamtrackaudiosourcenode) is created using `createMediaStreamTrackSource()`, taking its audio from the first audio track in the stream returned by `getUserMedia()`.

Then a [`BiquadFilterNode`](../biquadfilternode) is created using [`createBiquadFilter()`](../baseaudiocontext/createbiquadfilter), and it's configured as desired to perform a lowshelf filter on the audio coming from the source. The output from the microphone is then routed into the new biquad filter, and the filter's output is in turn routed to the audio context's [`destination`](../baseaudiocontext/destination).

    navigator.mediaDevices.getUserMedia ({audio: true, video: false})
    .then(function(stream) {
      audio.srcObject = stream;
      audio.onloadedmetadata = function(e) {
        audio.play();
        audio.muted = true;
      };

      let audioCtx = new AudioContext();
      let source = audioCtx.createMediaStreamSource(stream);

      let biquadFilter = audioCtx.createBiquadFilter();
      biquadFilter.type = "lowshelf";
      biquadFilter.frequency.value = 3000;
      biquadFilter.gain.value = 20;

      source.connect(biquadFilter);
      biquadFilter.connect(audioCtx.destination);
    })
    .catch(function(err) {
      // Handle getUserMedia() error
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audiocontext-createmediastreamtracksource">Web Audio API<br />
<span class="small">The definition of 'createMediaStreamTrackSource()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`createMediaStreamTrackSource`

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

## See also

- Web Audio API
- [Using the Web Audio API](../web_audio_api/using_web_audio_api)
- <span class="page-not-created">`MediaStreamTrackAudioSource`</span>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioContext/createMediaStreamTrackSource" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioContext/createMediaStreamTrackSource</a>
