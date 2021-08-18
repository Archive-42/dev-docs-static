RTCTrackEvent.receiver
======================

The read-only `receiver` property of the [`RTCTrackEvent`](../rtctrackevent) interface indicates the [`RTCRtpReceiver`](../rtcrtpreceiver) which is used to receive data containing media for the [`track`](track) to which the event refers.

Syntax
------

    var rtpReceiver = trackEvent.receiver;

### Value

The [`RTCRtpTransceiver`](../rtcrtptransceiver) which pairs the `receiver` with a sender and other properties which establish a single bidirectional [SRTP](https://developer.mozilla.org/en-US/docs/Glossary/RTP) stream for use by the [`track`](track) associated with the `RTCTrackEvent`.

**Note:** The [`transceiver`](transceiver) includes its own [`receiver`](../rtcrtptransceiver/receiver) property, which will always be the same [`RTCRtpReceiver`](../rtcrtpreceiver) as this one.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-trackevent-receiver">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCTrackEvent.receiver' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`receiver`

56

≤18

22

No

43

11

56

56

44

43

11

6.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEvent/receiver" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEvent/receiver</a>
