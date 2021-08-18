# AudioTrack.id

The `id` property contains a string which uniquely identifies the track represented by the **[`AudioTrack`](../audiotrack)**. This ID can be used with the [`AudioTrackList.getTrackById()`](../audiotracklist/gettrackbyid) method to locate a specific track within the media associated with a media element.

The track ID can also be used as the fragment of a URL that loads the specific track (if the media supports media fragments).

## Syntax

    var trackID = AudioTrack.id;

### Value

A [`DOMString`](../domstring) which identifies the track, suitable for use when calling [`getTrackById()`](../audiotracklist/gettrackbyid) on an [`AudioTrackList`](../audiotracklist) such as the one specified by a media element's [`audioTracks`](../htmlmediaelement/audiotracks) property.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/media.html#dom-audiotrack-id">HTML Living Standard<br />
<span class="small">The definition of 'AudioTrack.id' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#dom-audiotrack-id">HTML5<br />
<span class="small">The definition of 'AudioTrack.id' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`id`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioTrack/id" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioTrack/id</a>
