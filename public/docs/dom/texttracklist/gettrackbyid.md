TextTrackList.getTrackById()
============================

The **[`TextTrackList`](../texttracklist)** method `getTrackById()` returns the first [`TextTrack`](../texttrack) object from the track list whose `id` matches the specified string. This lets you find a specified track if you know its ID string.

Syntax
------

    var theTrack = TextTrackList.getTrackById(id);

### Parameters

`id`  
A [`DOMString`](../domstring) indicating the ID of the track to locate within the track list.

### Return value

A [`TextTrack`](../texttrack) object indicating the first track found within the `TextTrackList` whose `id` matches the specified string. If no match is found, this method returns `null`.

The tracks are searched in their natural order; that is, in the order defined by the media resource itself, or, if the resource doesn't define an order, the relative order in which the tracks are declared by the media resource.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-texttracklist-gettrackbyid">HTML Living Standard<br />
<span class="small">The definition of 'TextTrackList.getTrackById()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

33

18

Yes

No

20

7

4.4.3

33

?

20

8

2.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TextTrackList/getTrackById" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TextTrackList/getTrackById</a>
