VideoTrackList.onremovetrack
============================

The **[`VideoTrackList`](../videotracklist)** `onremovetrack` event handler is called when the `removetrack` event occurs, indicating that a video track has been removed from the media element, and therefore also from the `VideoTrackList`.

The event is passed into the event handler in the form of a [`TrackEvent`](../trackevent) object, whose [`track`](../trackevent/track) property identifies the track that was removed from the media element's `VideoTrackList`.

**Note:** You can also add a handler for the `removetrack` event using [`addEventListener()`](../eventtarget/addeventlistener).

Syntax
------

    VideoTrackList.onremovetrack = eventHandler;

### Value

Set `onremovetrack` to a function that accepts as input a [`TrackEvent`](../trackevent) object which indicates in its [`track`](../trackevent/track) property which video track has been removed from the media element.

Example
-------

This simple example just fetches the current number of video tracks in the media element whenever a track is removed from the media element.

    document.querySelector("my-video").videoTracks.onremovetrack = function(event) {
      myTrackCount = document.querySelector("my-video").videoTracks.length;
    };

The current number of video tracks remaining in the media element is obtained from `VideoTrackList` property [`length`](length).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#handler-tracklist-onremovetrack">HTML Living Standard<br />
<span class="small">The definition of 'VideoTrackList: onremovetrack' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`onremovetrack`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VideoTrackList/onremovetrack" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VideoTrackList/onremovetrack</a>
