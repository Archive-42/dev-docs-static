RTCRtpTransceiver.mid
=====================

The read-only [`RTCRtpTransceiver`](../rtcrtptransceiver) interface's `mid` property specifies the negotiated media ID (`mid`) which the local and remote peers have agreed upon to uniquely identify the stream's pairing of sender and receiver.

Syntax
------

    var mediaID = RTCRtpTransceiver.mid;

### Value

A [`DOMString`](../domstring) which uniquely identifies the pairing of source and destination of the transceiver's stream. Its value is taken from the media ID of the SDP m-line. This value is `null` if negotiation has not completed.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtptransceiver-mid">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCRtpTransceiver.mid' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`mid`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpTransceiver/mid" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpTransceiver/mid</a>
