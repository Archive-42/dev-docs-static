RTCRtpTransceiver.sender
========================

The read-only `sender` property of WebRTC's [`RTCRtpTransceiver`](../rtcrtptransceiver) interface indicates the [`RTCRtpSender`](../rtcrtpsender) responsible for encoding and sending outgoing media data for the transceiver's stream.

Syntax
------

    var rtpSender = RTCRtpTransceiver.sender;

### Value

An [`RTCRtpSender`](../rtcrtpsender) object used to encode and send media whose media ID matches the current value of [`mid`](mid).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcrtptransceiver-sender">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCRtpTransceiver.sender' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`sender`

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
-   [`RTCRtpSender`](../rtcrtpsender)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpTransceiver/sender" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpTransceiver/sender</a>
