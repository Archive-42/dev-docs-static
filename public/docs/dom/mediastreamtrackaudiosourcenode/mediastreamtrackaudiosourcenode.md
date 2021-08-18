# MediaStreamTrackAudioSourceNode()

The [Web Audio API](../web_audio_api)'s `MediaStreamTrackAudioSourceNode()` constructor creates and returns a new [`MediaStreamTrackAudioSourceNode`](../mediastreamtrackaudiosourcenode) object whose audio is taken from the [`MediaStreamTrack`](../mediastreamtrack) specified in the given options object.

Another way to create a `MediaStreamTrackAudioSourceNode` is to call the[`AudioContext.createMediaStreamTrackSource()`](../audiocontext/createmediastreamtracksource) method, specifying the [`MediaStreamTrack`](../mediastreamtrack) from which you want to obtain audio.

## Syntax

    audioTrackNode = new MediaStreamTrackAudioSourceNode(context, options);

### Parameters

`context`  
An [`AudioContext`](../audiocontext) representing the audio context you want the node to be associated with.

`options`  
A [`MediaStreamTrackAudioSourceOptions`](../mediastreamtrackaudiosourceoptions) object defining the properties you want the `MediaStreamTrackAudioSourceNode` to have:

[`mediaStreamTrack`](../mediastreamtrackaudiosourceoptions/mediastreamtrack)  
The [`MediaStreamTrack`](../mediastreamtrack) from which to take audio data for this node's output.

### Return value

A new [`MediaStreamTrackAudioSourceNode`](../mediastreamtrackaudiosourcenode) object representing the audio node whose media is obtained from the specified media track.

### Exceptions

`NotSupportedError`  
The specified `context` is not an [`AudioContext`](../audiocontext).

`InvalidStateError`  
The specified [`MediaStreamTrack`](../mediastreamtrack) isn't an audio track (that is, its [`kind`](../mediastreamtrack/kind) property isn't `audio`.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-mediastreamtrackaudiosourcenode-mediastreamtrackaudiosourcenode">Web Audio API<br />
<span class="small">The definition of 'MediaStreamTrackAudioSourceNode()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrackAudioSourceNode/MediaStreamTrackAudioSourceNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrackAudioSourceNode/MediaStreamTrackAudioSourceNode</a>
