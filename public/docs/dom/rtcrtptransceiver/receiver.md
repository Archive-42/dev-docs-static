RTCRtpTransceiver.receiver
==========================

The read-only `receiver` property of WebRTC's [`RTCRtpTransceiver`](../rtcrtptransceiver) interface indicates the [`RTCRtpReceiver`](../rtcrtpreceiver) responsible for receiving and decoding incoming media data for the transceiver's stream.

Syntax
------

    var rtpReceiver = RTCRtpTransceiver.receiver;

### Value

An [`RTCRtpReceiver`](../rtcrtpreceiver) object which is responsible for receiving and decoding incoming media data whose media ID is the same as the current value of [`mid`](mid).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcrtptransceiver-receiver">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCRtpTransceiver.receiver' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

69

No

59

No

No

11

69

69

59

No

11

10.0

See also
--------

-   [Introduction to the Real-time Transport Protocol (RTP)](../webrtc_api/intro_to_rtp)
-   [`RTCRtpReceiver`](../rtcrtpreceiver)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpTransceiver/receiver" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpTransceiver/receiver</a>
