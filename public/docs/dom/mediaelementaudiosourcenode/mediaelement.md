MediaElementAudioSourceNode.mediaElement
========================================

The [`MediaElementAudioSourceNode`](../mediaelementaudiosourcenode) interface's read-only `mediaElement` property indicates the [`HTMLMediaElement`](../htmlmediaelement) that contains the audio track from which the node is receiving audio. This stream was specified when the node was first created, either using the [`MediaElementAudioSourceNode()`](mediaelementaudiosourcenode) constructor or the [`AudioContext.createMediaElementSource()`](../audiocontext/createmediaelementsource) method.

Syntax
------

    audioSourceElement = mediaElementAudioSourceNode.mediaElement;

### Value

An [`HTMLMediaElement`](../htmlmediaelement) representing the element which contains the source of audio for the node.

Examples
--------

    const audioCtx = new window.AudioContext();
    const audioElem = document.querySelector('audio');

    let options = {
      mediaElement: audioElem
    }

    let source = new MediaElementAudioSourceNode(audioCtx, options);
    console.log(source.mediaElement);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-mediaelementaudiosourcenode-mediaelement">Web Audio API<br />
<span class="small">The definition of 'MediaElementAudioSourceNode.mediaElement' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`mediaElement`

Yes

≤79

70

No

Yes

6

Yes

Yes

No

Yes

6

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaElementAudioSourceNode/mediaElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaElementAudioSourceNode/mediaElement</a>
