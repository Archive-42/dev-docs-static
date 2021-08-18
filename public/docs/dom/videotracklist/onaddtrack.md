VideoTrackList.onaddtrack
=========================

The **[`VideoTrackList`](../videotracklist)** property `onaddtrack` is an event handler which is called when the `addtrack` event occurs, indicating that a new video track has been added to the media element whose video tracks the `VideoTrackList` represents.

The event is passed into the event handler in the form of a [`TrackEvent`](../trackevent) object, whose [`track`](../trackevent/track) property identifies the newly-added track.

**Note:** You can also add a handler for the `addtrack` event using [`addEventListener()`](../eventtarget/addeventlistener).

Syntax
------

    VideoTrackList.onaddtrack = eventHandler;

### Value

Set `onaddtrack` to a function that accepts as input a [`TrackEvent`](../trackevent) object which indicates in its [`track`](../trackevent/track) property which video track has been added to the media.

Usage notes
-----------

The `addtrack` event is called whenever a new track is added to the media element whose video tracks are represented by the `VideoTrackList` object. This happens when tracks are added to the element when the media is first attached to the element; one `addtrack` event will occur for each video track in the media resource.

Example
-------

This snippet establishes a handler for the `addtrack` event that calls a function, `addToTrackList()`, passing in the [`VideoTrack`](../videotrack) object representing the newly-added track. In this scenario, that function's role is to add the new track to a list of video tracks available to choose from.

    document.querySelector("video").videoTracks.onaddtrack = function(event) {
      addToTrackList(event.track);
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#handler-tracklist-onaddtrack">HTML Living Standard<br />
<span class="small">The definition of 'VideoTrackList: onaddtrack' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`onaddtrack`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VideoTrackList/onaddtrack" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VideoTrackList/onaddtrack</a>
