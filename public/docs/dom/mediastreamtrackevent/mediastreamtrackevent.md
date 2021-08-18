MediaStreamTrackEvent()
=======================

The `MediaStreamTrackEvent()` constructor returns a newly created [`MediaStreamTrackEvent`](../mediastreamtrackevent) object, which represents an event announcing that a [`MediaStreamTrack`](../mediastreamtrack) has been added to or removed from a [`MediaStream`](../mediastream).

Syntax
------

    var trackEvent = new MediaStreamTrackEvent(type, {track: aMediaStreamTrack});

### Parameters

*The `MediaStreamTrackEvent()` constructor also inherits arguments from [`Event()`](../event/event).*

`type`  
A [`DOMString`](../domstring) representing the name of the type of the `MediaStreamTrackEvent`. It is case-sensitive and can be `"addtrack`" or `"removetrack`".

`track`  
A [`MediaStreamTrack`](../mediastreamtrack) object representing the track which was added to or removed from the stream.

### Return value

A new [`MediaStreamTrackEvent`](../mediastreamtrackevent), initialized based on the provided options.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediastreamtrackevent">Media Capture and Streams<br />
<span class="small">The definition of 'MediaStreamTrackEvent()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

See also
--------

-   `addtrack` and `removetrack` events
-   [`MediaStreamTrack`](../mediastreamtrack)
-   [`MediaStream`](../mediastream)
-   [Media Streams API](../media_streams_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrackEvent/MediaStreamTrackEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrackEvent/MediaStreamTrackEvent</a>
