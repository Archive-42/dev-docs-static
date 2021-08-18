# MediaStreamAudioSourceOptions.mediaStream

The [`MediaStreamAudioSourceOptions`](../mediastreamaudiosourceoptions) dictionary's `mediaStream` property must specify the [`MediaStream`](../mediastream) from which to retrieve audio data when instantiating a `MediaStreamAudioSourceNode` using the [`MediaStreamAudioSourceNode()`](../mediastreamaudiosourcenode/mediastreamaudiosourcenode) constructor.

## Syntax

    mediaStreamAudioSourceOptions = {
      mediaStream: audioSourceStream;
    }

    mediaStreamAudioSourceOptions.mediaStream = audioSourceStream;

### Value

A [`MediaStream`](../mediastream) representing the stream from which to use a [`MediaStreamTrack`](../mediastreamtrack) as the source of audio for the node.

## Example

This example uses [`getUserMedia()`](../mediadevices/getusermedia) to obtain access to the user's camera, then creates a new [`MediaStreamAudioSourceNode`](../mediastreamaudiosourcenode) from its [`MediaStream`](../mediastream).

    // define variables
    var audioCtx = new (window.AudioContext || window.webkitAudioContext)();

    // getUserMedia block - grab stream
    // put it into a MediaStreamAudioSourceNode
    if (navigator.mediaDevices.getUserMedia) {
       navigator.mediaDevices.getUserMedia (
          // constraints: audio and video for this app
          {
             audio: true,
             video: false
          }).then(function(stream) {
            var options = {
              mediaStream : stream
            }

            var source = new MediaStreamAudioSourceNode(audioCtx, options);
            source.connect(audioCtx.destination);
          }).catch(function(err) {
           console.log('The following gUM error occurred: ' + err);
          });
    } else {
      console.log('new getUserMedia not supported on your browser!');
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-mediastreamaudiosourceoptions-mediastream">Web Audio API<br />
<span class="small">The definition of 'MediaStreamAudioSourceOptions.mediaStream' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`mediaStream`

55

≤79

53

No

?

?

55

55

53

?

?

6.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamAudioSourceOptions/mediaStream" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamAudioSourceOptions/mediaStream</a>
