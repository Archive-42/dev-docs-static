VideoTrackList.getTrackById()
=============================

The **[`VideoTrackList`](../videotracklist)** method `getTrackById()` returns the first [`VideoTrack`](../videotrack) object from the track list whose [`id`](../videotrack/id) matches the specified string. This lets you find a specified track if you know its ID string.

Syntax
------

    var theTrack = VideoTrackList.getTrackById(id);

### Parameters

`id`  
A [`DOMString`](../domstring) indicating the ID of the track to locate within the track list.

### Return value

A [`VideoTrack`](../videotrack) object indicating the first track found within the `VideoTrackList` whose `id` matches the specified string. If no match is found, this method returns `null`.

The tracks are searched in their natural order; that is, in the order defined by the media resource itself, or, if the resource doesn't define an order, the relative order in which the tracks are declared by the media resource.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-videotracklist-gettrackbyid">HTML Living Standard<br />
<span class="small">The definition of 'VideoTrackList.getTrackById()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`getTrackById`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VideoTrackList/getTrackById" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VideoTrackList/getTrackById</a>
