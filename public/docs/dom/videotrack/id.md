VideoTrack.id
=============

The `id` property contains a string which uniquely identifies the track represented by the **[`VideoTrack`](../videotrack)**. This ID can be used with the [`VideoTrackList.getTrackById()`](../videotracklist/gettrackbyid) method to locate a specific track within the media associated with a media element.

The track ID can also be used as the fragment of a URL that loads the specific track (if the media supports media fragments).

Syntax
------

    var trackID = VideoTrack.id;

### Value

A [`DOMString`](../domstring) which identifies the track, suitable for use when calling [`getTrackById()`](../videotracklist/gettrackbyid) on an [`VideoTrackList`](../videotracklist) such as the one specified by a media element's [`videoTracks`](../htmlmediaelement/videotracks) property.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-videotrack-id">HTML Living Standard<br />
<span class="small">The definition of 'VideoTrack: id' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VideoTrack/id" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VideoTrack/id</a>
