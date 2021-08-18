HTMLMediaElement.videoTracks
============================

**Draft**

This page is not complete.

The read-only `videoTracks` property on [`HTMLMediaElement`](../htmlmediaelement) objects returns a [`VideoTrackList`](../videotracklist) object listing all of the [`VideoTrack`](../videotrack) objects representing the media element's video tracks.

The returned list is *live*; that is, as tracks are added to and removed from the media element, the list's contents change dynamically. Once you have a reference to the list, you can monitor it for changes to detect when new video tracks are added or existing ones removed. See [Event handlers](#) in [VideoTrackList](../videotracklist) to learn more about watching for changes to a media element's track list.

Syntax
------

    var videoTracks = mediaElement.videoTracks;

### Value

A [`VideoTrackList`](../videotracklist) object representing the list of video tracks included in the media element. The list of tracks can be accessed using array notation, or using the object's [`getTrackById()`](../videotracklist/gettrackbyid) method.

Each track is represented by a [`VideoTrack`](../videotrack) object which provides information about the track.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-media-videotracks">HTML Living Standard<br />
<span class="small">The definition of 'HTMLMediaElement.videoTracks' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/html52/">HTML5</a></td></tr></tbody></table>

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

`videoTracks`

37

79

12-79

33

No

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
-   [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video)
-   [`VideoTrack`](../videotrack) and [`VideoTrackList`](../videotracklist)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/videoTracks" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/videoTracks</a>
