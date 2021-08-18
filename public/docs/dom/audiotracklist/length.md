# AudioTrackList.length

The read-only **[`AudioTrackList`](../audiotracklist)** property `length` returns the number of entries in the `AudioTrackList`, each of which is an [`AudioTrack`](../audiotrack) representing one audio track in the media element. A value of 0 indicates that there are no audio tracks in the media.

## Syntax

    var trackCount = AudioTrackList.length;

### Value

A number indicating how many audio tracks are included in the `AudioTrackList`. Each track can be accessed by treating the `AudioTrackList` as an array of objects of type [`AudioTrack`](../audiotrack).

## Example

This snippet gets the number of audio tracks in the first [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element found in the [DOM](https://developer.mozilla.org/en-US/docs/Glossary/DOM) by [`querySelector()`](../document/queryselector).

    var videoElem = document.querySelector("video");
    var numAudioTracks = 0;

    if (videoElem.audioTracks) {
      numAudioTracks = videoElem.audioTracks.length;
    }

Note that this sample checks to be sure [`HTMLMediaElement.audioTracks`](../htmlmediaelement/audiotracks) is defined, to avoid failing on browsers without support for [`AudioTrack`](../audiotrack).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/media.html#dom-audiotracklist-length">HTML Living Standard<br />
<span class="small">The definition of 'AudioTrackList.length' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#dom-audiotracklist-length">HTML5<br />
<span class="small">The definition of 'AudioTrackList.length' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`length`

37

79

12-79

33

10

24

6.1

No

37

33

24

7

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioTrackList/length" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioTrackList/length</a>
