# AudioTrack.sourceBuffer

The read-only **[`AudioTrack`](../audiotrack)** property `sourceBuffer` returns the [`SourceBuffer`](../sourcebuffer) that created the track, or null if the track was not created by a [`SourceBuffer`](../sourcebuffer) or the [`SourceBuffer`](../sourcebuffer) has been removed from the [`MediaSource.sourceBuffers`](../mediasource/sourcebuffers) attribute of its parent media source.

## Syntax

    var sourceBuffer = AudioTrack.sourceBuffer;

### Value

A [`SourceBuffer`](../sourcebuffer) or null.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/media-source/#dom-audiotrack-sourcebuffer">Media Source Extensions<br />
<span class="small">The definition of 'AudioTrack: sourceBuffer' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`sourceBuffer`

51

79

12-79

No

11

38

6.1

No

51

No

41

7

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioTrack/sourceBuffer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioTrack/sourceBuffer</a>
