HTMLMediaElement.audioTracks
============================

**Draft**

This page is not complete.

The read-only `audioTracks` property on [`HTMLMediaElement`](../htmlmediaelement) objects returns an [`AudioTrackList`](../audiotracklist) object listing all of the [`AudioTrack`](../audiotrack) objects representing the media element's audio tracks. The media element may be either an [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) element or a [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element.

The returned list is *live*; that is, as tracks are added to and removed from the media element, the list's contents change dynamically. Once you have a reference to the list, you can monitor it for changes to detect when new audio tracks are added or existing ones removed. See [Event handlers](#) in [AudioTrackList](../audiotracklist) to learn more about watching for changes to a media element's track list.

Syntax
------

    var audioTracks = mediaElement.audioTracks;

### Value

A [`AudioTrackList`](../audiotracklist) object representing the list of audio tracks included in the media element. The list of tracks can be accessed using array notation, or using the object's [`getTrackById()`](../audiotracklist/gettrackbyid) method.

Each track is represented by a [`AudioTrack`](../audiotrack) object which provides information about the track.

Examples
--------

In this example, all of the audio tracks on a given element are muted.

### HTML

The HTML establishes the element itself.

    <video id="video" src="somevideo.mp4"></video>

### JavaScript

The JavaScript code handles muting the video element's audio tracks.

    var video = document.getElementById("video");

    for (var i = 0; i < video.audioTracks.length; i += 1) {
      video.audioTracks[i].enabled = false;
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-media-audiotracks">HTML Living Standard<br />
<span class="small">The definition of 'HTMLMediaElement.audioTracks' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/html52/">HTML5</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#htmlmediaelement">HTML5<br />
<span class="small">The definition of 'HTMLMediaElement.audioTracks' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`audioTracks`

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

6.1

No

See also
--------

-   The interface defining it, [`HTMLMediaElement`](../htmlmediaelement).
-   [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) and [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video)
-   [`AudioTrack`](../audiotrack) and [`AudioTrackList`](../audiotracklist)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/audioTracks" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/audioTracks</a>
