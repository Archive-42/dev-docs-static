VideoTrackList
==============

The `VideoTrackList` interface is used to represent a list of the video tracks contained within a [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element, with each track represented by a separate [`VideoTrack`](videotrack) object in the list.

Retrieve an instance of this object with [`HTMLMediaElement.videoTracks`](htmlmediaelement/videotracks). The individual tracks can be accessed using array syntax or functions such as [`forEach()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach) for example.

Properties
----------

*This interface also inherits properties from its parent interface, [`EventTarget`](eventtarget).*

 [`length`](videotracklist/length) <span class="badge inline readonly">Read only </span>   
The number of tracks in the list.

 [`selectedIndex`](videotracklist/selectedindex) <span class="badge inline readonly">Read only </span>   
The index of the currently selected track, if any, or `−1` otherwise.

Event handlers
--------------

[`onaddtrack`](videotracklist/onaddtrack)  
An event handler to be called when the `addtrack` event is fired, indicating that a new video track has been added to the media element.

[`onchange`](videotracklist/onchange)  
An event handler to be called when the `change` event occurs — that is, when the value of the [`selected`](videotrack/selected) property for a track has changed, due to the track being made active or inactive.

[`onremovetrack`](videotracklist/onremovetrack)  
An event handler to call when the `removetrack` event is sent, indicating that a video track has been removed from the media element.

Methods
-------

*This interface also inherits methods from its parent interface, [`EventTarget`](eventtarget).*

[`getTrackById()`](videotracklist/gettrackbyid)  
Returns the [`VideoTrack`](videotrack) found within the `VideoTrackList` whose [`id`](videotrack/id) matches the specified string. If no match is found, `null` is returned.

Events
------

[`addtrack`](videotracklist/addtrack_event)  
Fired when a new video track has been added to the media element.  
Also available via the [`onaddtrack`](videotracklist/onaddtrack) property.

[`change`](videotracklist/change_event)  
Fired when a video track has been made active or inactive.  
Also available via the [`onchange`](videotracklist/onchange) property.

[`removetrack`](videotracklist/removetrack_event)  
Fired when a new video track has been removed from the media element.  
Also available via the [`onremovetrack`](videotracklist/onremovetrack) property.

Usage notes
-----------

In addition to being able to obtain direct access to the video tracks present on a media element, `VideoTrackList` lets you set event handlers on the `addtrack` and `removetrack` events, so that you can detect when tracks are added to or removed from the media element's stream. See [`onaddtrack`](videotracklist/onaddtrack) and [`onremovetrack`](videotracklist/onremovetrack) for details and examples.

Examples
--------

### Getting a media element's video track list

To get a media element's [`VideoTrackList`](videotracklist), use its [`videoTracks`](htmlmediaelement/videotracks) property.

    var videoTracks = document.querySelector("video").videoTracks;

### Monitoring track count changes

In this example, we have an app that displays information about the number of channels available. To keep it up to date, handlers for the `addtrack` and `removetrack` events are set up.

    videoTracks.onaddtrack = updateTrackCount;
    videoTracks.onremovetrack = updateTrackCount;

    function updateTrackCount(event) {
      trackCount = videoTracks.length;
      drawTrackCountIndicator(trackCount);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#videotracklist">HTML Living Standard<br />
<span class="small">The definition of 'VideoTrackList' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`VideoTrackList`

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

`addtrack_event`

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

`change_event`

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

`onchange`

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

`removetrack_event`

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

`selectedIndex`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VideoTrackList" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VideoTrackList</a>
