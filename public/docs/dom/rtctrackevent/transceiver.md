RTCTrackEvent.transceiver
=========================

The WebRTC API interface [`RTCTrackEvent`](../rtctrackevent)'s read-only `transceiver` property indicates the [`RTCRtpTransceiver`](../rtcrtptransceiver) affiliated with the event's [`track`](track). The transceiver pairs the track's [`receiver`](receiver) with an [`RTCRtpSender`](../rtcrtpsender).

Syntax
------

    var rtpTransceiver = trackEvent.transceiver;

### Value

The [`RTCRtpTransceiver`](../rtcrtptransceiver) which pairs the `receiver` with a sender and other properties which establish a single bidirectional [SRTP](https://developer.mozilla.org/en-US/docs/Glossary/RTP) stream for use by the [`track`](track) associated with the `RTCTrackEvent`.

**Note:** The [`RTCRtpReceiver`](../rtcrtpreceiver) referred to by this `RTCRtpReceiver`'s [`receiver`](../rtcrtptransceiver/receiver) property will always be the same as the [`RTCTrackEvent`](../rtctrackevent)'s [`receiver`](receiver) property.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-trackevent-transceiver">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCTrackEvent.transceiver' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`transceiver`

69

≤18

59

No

43

11

69

69

59

43

11

6.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEvent/transceiver" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEvent/transceiver</a>
