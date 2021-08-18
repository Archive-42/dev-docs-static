RTCTrackEventInit
=================

The WebRTC API's `RTCTrackEventInit` dictionary is used to provide information describing an [`RTCTrackEvent`](rtctrackevent) when instantiating a new `track` event using [`new RTCTrackEvent()`](rtctrackevent/rtctrackevent).

Properties
----------

*`RTCTrackEventInit` inherits properties from the <span class="page-not-created">`EventInit`</span> dictionary, and also includes the following properties:*

[`receiver`](rtctrackeventinit/receiver)  
The [`RTCRtpReceiver`](rtcrtpreceiver) which is being used to receive the track's media.

 [`streams`](rtctrackeventinit/streams) <span class="badge inline optional">Optional</span>   
An array of [`MediaStream`](mediastream) objects representing each of the streams that comprise the event's corresponding track.

[`track`](rtctrackeventinit/track)  
The [`MediaStreamTrack`](mediastreamtrack) the event is associated with.

[`transceiver`](rtctrackevent/transceiver)  
The [`RTCRtpTransceiver`](rtcrtptransceiver) associated with the event.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtctrackeventinit">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCTrackEventInit' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`RTCTrackEventInit`

56

≤18

22

No

43

?

56

56

44

43

?

6.0

`receiver`

56

≤18

22

No

43

?

56

56

44

43

?

6.0

`streams`

56

≤18

22

No

43

?

56

56

44

43

?

6.0

`track`

56

≤18

22

No

43

?

56

56

44

43

?

6.0

`transceiver`

69

≤18

59

No

43

?

69

69

59

43

?

6.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEventInit" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEventInit</a>
