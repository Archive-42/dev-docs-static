TextTrackList.onremovetrack
===========================

The **[`TextTrackList`](../texttracklist)** `onremovetrack` event handler is called when the `removetrack` event occurs, indicating that a text track has been removed from the media element, and therefore also from the `TextTrackList`.

The event is passed into the event handler in the form of a [`TrackEvent`](../trackevent) object, whose [`track`](../trackevent/track) property identifies the track that was removed from the media element's `TextTrackList`.

**Note:** You can also add a handler for the `removetrack` event using [`addEventListener()`](../eventtarget/addeventlistener).

Syntax
------

    TextTrackList.onremovetrack = eventHandler;

### Value

Set `onremovetrack` to a function that accepts as input a [`TrackEvent`](../trackevent) object which indicates in its [`track`](../trackevent/track) property which text track has been removed from the media element.

Example
-------

This simple example just fetches the current number of text tracks in the first media element whenever a track is removed from the media element.

    document.querySelectorAll("video, audio")[0].textTracks.onremovetrack = function(event) {
      myTrackCount = document.querySelectorAll("video, audio")[0].textTracks.length;
    };

The current number of text tracks remaining in the media element is obtained from `TextTrackList` property [`length`](length).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#handler-tracklist-onremovetrack">HTML Living Standard<br />
<span class="small">The definition of 'TextTrackList: onremovetrack' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

33

18

31

No

20

≤12.1-15

6.1

4.4

33

31

20

≤12.1-14

7

2.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TextTrackList/onremovetrack" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TextTrackList/onremovetrack</a>
