# MediaStreamAudioSourceNode()

The [Web Audio API](../web_audio_api)'s `MediaStreamAudioSourceNode()` constructor creates and returns a new [`MediaStreamAudioSourceNode`](../mediastreamaudiosourcenode) object which uses the first audio track of a given [`MediaStream`](../mediastream) as its source.

**Note:** Another way to create a `MediaStreamAudioSourceNode` is to call the[`AudioContext.createMediaStreamSource()`](../audiocontext/createmediastreamsource) method, specifying the stream from which you want to obtain audio.

## Syntax

    audioSourceNode = new MediaStreamAudioSourceNode(context, options);

### Parameters

`context`  
An [`AudioContext`](../audiocontext) representing the audio context you want the node to be associated with.

`options`  
A [`MediaStreamAudioSourceOptions`](../mediastreamaudiosourceoptions) object defining the properties you want the `MediaStreamAudioSourceNode` to have:

[`mediaStream`](../mediastreamaudiosourceoptions/mediastream)  
A required property which specifies the [`MediaStream`](../mediastream) from which to obtain audio for the node.

### Return value

A new [`MediaStreamAudioSourceNode`](../mediastreamaudiosourcenode) object representing the audio node whose media is obtained from the specified source stream.

### Exceptions

`InvalidStateError`  
The specified [`MediaStream`](../mediastream) doesn't have any audio tracks.

## Examples

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-mediastreamaudiosourcenode-mediastreamaudiosourcenode">Web Audio API<br />
<span class="small">The definition of 'MediaStreamAudioSourceNode()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamAudioSourceNode/MediaStreamAudioSourceNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamAudioSourceNode/MediaStreamAudioSourceNode</a>
