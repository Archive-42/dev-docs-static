# MediaStreamTrackAudioSourceOptions.mediaStreamTrack

The [`MediaStreamTrackAudioSourceOptions`](../mediastreamtrackaudiosourceoptions) dictionary's `mediaStreamTrack` property must contain a reference to the [`MediaStreamTrack`](../mediastreamtrack) from which the `MediaStreamTrackAudioSourceNode` being created using the [`MediaStreamTrackAudioSourceNode()`](../mediastreamtrackaudiosourcenode/mediastreamtrackaudiosourcenode) constructor.

## Syntax

    mediaStreamTrackAudioSourceOptions = {
      mediaStreamTrack: audioSourceTrack;
    }

    mediaStreamTrackAudioSourceOptions.mediaStreamTrack = audioSourceTrack;

### Value

A [`MediaStreamTrack`](../mediastreamtrack) from which the audio output of the new `MediaStreamTrackAudioSourceNode` will be taken.

## Example

This example uses [`getUserMedia()`](../mediadevices/getusermedia) to obtain access to the user's camera, then creates a new [`MediaStreamAudioSourceNode`](../mediastreamaudiosourcenode) from the first audio track provided by the device.

    let audioCtx = new (window.AudioContext || window.webkitAudioContext)();

    if (navigator.mediaDevices.getUserMedia) {
      navigator.mediaDevices.getUserMedia (
        {
          audio: true,
          video: false
        }).then(function(stream) {
          let options = {
            mediaStreamTrack: stream.getAudioTracks()[0];
          }

          let source = new MediaStreamTrackAudioSourceNode(audioCtx, options);
          source.connect(audioCtx.destination);
        }).catch(function(err) {
          console.log('The following gUM error occurred: ' + err);
        });
    } else {
      console.log('new getUserMedia not supported on your browser!');
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-mediastreamtrackaudiosourceoptions-mediastreamtrack">Web Audio API<br />
<span class="small">The definition of 'MediaStreamTrackAudioSourceOptions.mediaStream' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrackAudioSourceOptions/mediaStreamTrack" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrackAudioSourceOptions/mediaStreamTrack</a>
