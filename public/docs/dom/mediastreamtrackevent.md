MediaStreamTrackEvent
=====================

The `MediaStreamTrackEvent` interface represents events which indicate that a [`MediaStream`](mediastream) has had tracks added to or removed from the stream through calls to [Media Stream API](media_streams_api) methods. These events are sent to the stream when these changes occur.

The events based on this interface are `addtrack` and `removetrack`

Properties
----------

*Also inherits properties from its parent interface, [`Event`](event).*

 `track` <span class="badge inline readonly">Read only </span>   
A [`MediaStreamTrack`](mediastreamtrack) object representing the track which was added to the stream.

Constructor
-----------

[`MediaStreamTrackEvent()`](mediastreamtrackevent/mediastreamtrackevent)  
Constructs a new `MediaStreamTrackEvent` with the specified configuration.

Methods
-------

*Also inherits methods from its parent [`Event`](event).*

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#mediastreamtrackevent">Media Capture and Streams<br />
<span class="small">The definition of 'MediaStreamTrackEvent' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`MediaStreamTrackEvent`

55

12

50

No

42

Yes

55

55

50

42

Yes

6.0

`MediaStreamTrackEvent`

55

12

50

No

42

Yes

55

55

50

42

Yes

6.0

`track`

Yes

12

Yes

No

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   `addtrack` and `removetrack` events
-   [`MediaStream`](mediastream): [`onaddtrack`](mediastream/onaddtrack) and [`onremovetrack`](mediastream/onremovetrack)
-   [`MediaStreamTrack`](mediastreamtrack)
-   [Media Streams API](media_streams_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrackEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrackEvent</a>
