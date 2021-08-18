TextTrackList.onchange
======================

The **[`TextTrackList`](../texttracklist)** property `onchange` is an event handler which is called when the `change` event occurs, indicating that a change has occurred on a [`TextTrack`](../texttrack) in the `VideoTrackList`.

**Note:** You can also add a handler for the `change` event using [`addEventListener()`](../eventtarget/addeventlistener).

Syntax
------

    TextTrackList.onchange = eventHandler;

Example
-------

This snippet establishes a handler for the `change` event that looks at each of the tracks in the list, calling a function to update the state of a user interface control that indicates the current state of the track.

    var trackList = document.querySelector("video, audio").textTracks;

    trackList.onchange = function(event) {
       .... /* do something */
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#handler-tracklist-onchange">HTML Living Standard<br />
<span class="small">The definition of 'TextTrackList: onchange' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`onchange`

33

18

31

No

20

7

4.4

33

31

20

7

2.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TextTrackList/onchange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TextTrackList/onchange</a>
