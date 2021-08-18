TextTrackList
=============

The `TextTrackList` interface is used to represent a list of the text tracks defined by the [`<track>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/track) element, with each track represented by a separate [`textTrack`](texttrack) object in the list.

Retrieve an instance of this object with [`HTMLMediaElement.textTracks`](htmlmediaelement/texttracks). The individual tracks can be accessed using array syntax or functions such as [`forEach()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach) for example.

Properties
----------

*This interface also inherits properties from its parent interface, [`EventTarget`](eventtarget).*

 [`length`](texttracklist/length) <span class="badge inline readonly">Read only </span>   
The number of tracks in the list.

Event handlers
--------------

[`onaddtrack`](texttracklist/onaddtrack)  
An event handler to be called when the `addtrack` event is fired, indicating that a new text track has been added to the media element.

[`onchange`](texttracklist/onchange)  
An event handler to be called when the `change` event occurs.

[`onremovetrack`](texttracklist/onremovetrack)  
An event handler to call when the `removetrack` event is sent, indicating that a text track has been removed from the media element.

Methods
-------

*This interface also inherits methods from its parent interface, [`EventTarget`](eventtarget).*

[`getTrackById()`](texttracklist/gettrackbyid)  
Returns the [`TextTrack`](texttrack) found within the `TextTrackList` whose <span class="page-not-created">`id`</span> matches the specified string. If no match is found, `null` is returned.

Events
------

`addtrack`  
Fired when a new text track has been added to the media element.  
Also available via the `onaddtrack` property.

`change`  
Fired when a text track has been made active or inactive.  
Also available via the `onchange` property.

`removetrack`  
Fired when a new text track has been removed from the media element.  
Also available via the `onremovetrack` property.

Usage notes
-----------

In addition to being able to obtain direct access to the text tracks present on a media element, `TextTrackList` lets you set event handlers on the `addtrack` and `removetrack` events, so that you can detect when tracks are added to or removed from the media element's stream. See [`onaddtrack`](texttracklist/onaddtrack) and [`onremovetrack`](texttracklist/onremovetrack) for details and examples.

Examples
--------

### Getting a video element's text track list

To get a media element's [`TextTrackList`](texttracklist), use its [`textTracks`](htmlmediaelement/texttracks) property.

    var textTracks = document.querySelector("video").textTracks;

### Monitoring track count changes

In this example, we have an app that displays information about the number of channels available. To keep it up to date, handlers for the `addtrack` and `removetrack` events are set up.

    textTracks.onaddtrack = updateTrackCount;
    textTracks.onremovetrack = updateTrackCount;

    function updateTrackCount(event) {
      trackCount = textTracks.length;
      drawTrackCountIndicator(trackCount);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#texttracklist">HTML Living Standard<br />
<span class="small">The definition of 'TexTrackList' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`TextTrackList`

23

≤18

Yes

10

≤12.1

6

≤37

25

Yes

≤12.1

7

1.5

`addTrack_event`

Yes

≤79

?

?

?

?

Yes

Yes

?

?

?

Yes

`change_event`

Yes

≤79

?

?

?

?

Yes

Yes

?

?

?

Yes

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

`length`

44

≤18

Yes

10

31

6

44

44

?

32

7

4.0

`onaddtrack`

23

12

31

11

≤12.1

6

≤37

25

31

≤12.1

7

1.5

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

`removeTrack_event`

Yes

≤79

?

?

?

?

Yes

Yes

?

?

?

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TextTrackList" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TextTrackList</a>
