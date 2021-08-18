# MediaStreamAudioSourceNode.mediaStream

The [`MediaStreamAudioSourceNode`](../mediastreamaudiosourcenode) interface's read-only `mediaStream` property indicates the [`MediaStream`](../mediastream) that contains the audio track from which the node is receiving audio. This stream was specified when the node was first created, either using the [`MediaStreamAudioSourceNode()`](mediastreamaudiosourcenode) constructor or the [`AudioContext.createMediaStreamSource()`](../audiocontext/createmediastreamsource) method.

## Syntax

    audioSourceStream = mediaStreamAudioSourceNode.mediaStream;

### Value

A [`MediaStream`](../mediastream) representing the stream which contains the [`MediaStreamTrack`](../mediastreamtrack) serving as the source of audio for the node.

The [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) uses the first audio track it finds on the specified stream as the audio source for this node. However, there is no way to be certain which track that will be on multi-track streams. If the specific track matters to you, or you need to have access to the track itself, you should use a [`MediaStreamTrackAudioSourceNode`](../mediastreamtrackaudiosourcenode) instead.

## Examples

    const audioCtx = new window.AudioContext();
    let options = {
      mediaStream : stream
    }

    let source = new MediaStreamAudioSourceNode(audioCtx, options);
    console.log(source.mediaStream);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-mediastreamaudiosourcenode-mediastream">Web Audio API<br />
<span class="small">The definition of 'MediaStreamAudioSourceNode.mediaStream' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamAudioSourceNode/mediaStream" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamAudioSourceNode/mediaStream</a>
