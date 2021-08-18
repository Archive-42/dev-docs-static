VideoTrackList.length
=====================

The read-only **[`VideoTrackList`](../videotracklist)** property `length` returns the number of entries in the `VideoTrackList`, each of which is a [`VideoTrack`](../videotrack) representing one video track in the media element. A value of 0 indicates that there are no video tracks in the media.

Syntax
------

    var trackCount = VideoTrackList.length;

### Value

A number indicating how many video tracks are included in the `VideoTrackList`. Each track can be accessed by treating the `VideoTrackList` as an array of objects of type [`VideoTrack`](../videotrack).

Example
-------

This snippet gets the number of video tracks in the first [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element found in the [DOM](https://developer.mozilla.org/en-US/docs/Glossary/DOM) by [`querySelector()`](../document/queryselector).

    var videoElem = document.querySelector("video");
    var numVideoTracks = 0;

    if (videoElem.videoTracks) {
      numVideoTracks = videoElem.videoTracks.length;
    }

Note that this sample checks to be sure [`HTMLMediaElement.videoTracks`](../htmlmediaelement/videotracks) is defined, to avoid failing on browsers without support for [`VideoTrack`](../videotrack).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-videotracklist-length">HTML Living Standard<br />
<span class="small">The definition of 'VideoTrackList: length' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VideoTrackList/length" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VideoTrackList/length</a>
