RTCRtpTransceiverDirection
==========================

The `RTCRtpTransceiverDirection` type is an enumerated set of strings which are used to describe the directionality of a [`RTCRtpTransceiver`](rtcrtptransceiver) instance. Both the preferred [`direction`](rtcrtptransceiver/direction) and the [`currentDirection`](rtcrtptransceiver/currentdirection) properties are of this type.

Values
------

The `RTCRtpTransceiverDirection` type is an enumeration of string values. Each describes how the transceiver's associated [`RTCRtpSender`](rtcrtpsender) and [`RTCRtpReceiver`](rtcrtpreceiver) behave as shown in the table below.

<table><thead><tr class="header"><th>Value</th><th><code>RTCRtpSender</code> behavior</th><th><code>RTCRtpReceiver</code> behavior</th></tr></thead><tbody><tr class="odd"><td><span id="sendrecv"><code>"sendrecv"</code></span></td><td>Offers to send <a href="https://developer.mozilla.org/en-US/docs/Glossary/RTP">RTP</a> data, and will do so if the other peer accepts the connection and at least one of the sender's encodings is active<sup>1</sup>.</td><td>Offers to receive RTP data, and does so if the other peer accepts.</td></tr><tr class="even"><td><span id="sendonly"><code>"sendonly"</code></span></td><td>Offers to send RTP data, and will do so if the other peer accepts the connection and at least one of the sender's encodings is active<sup>1</sup>.</td><td>Does <em>not</em> offer to receive RTP data and will not do so.</td></tr><tr class="odd"><td><span id="recvonly"><code>"recvonly"</code></span></td><td>Does <em>not</em> offer to send RTP data, and will not do so.</td><td>Offers to receive RTP data, and will do so if the other peer offers.</td></tr><tr class="even"><td><span id="inactive"><code>"inactive"</code></span></td><td>Does <em>not</em> offer to send RTP data, and will not do so.</td><td>Does <em>not</em> offer to receive RTP data and will not do so.</td></tr></tbody></table>

\[1\] To determine if a sender has at least one active encoding, the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) gets its parameters using [`RTCRtpSender.getParameters()`](rtcrtpsender/getparameters), then looks at the parameters' <span class="page-not-created">`encodings`</span> property; if any of the listed encodings has its <span class="page-not-created">`active`</span> property set to `true`, the sender has an active encoding.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcrtptransceiverdirection">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCRtpTransceiverDirection' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`RTCRtpTransceiverDirection`

69

≤18

59

No

?

?

69

69

59

?

?

10.0

See also
--------

-   [WebRTC API](webrtc_api)
-   [Introduction to the Real-time Transport Protocol (RTP)](webrtc_api/intro_to_rtp)
-   [`RTCRtpTransceiver.direction`](rtcrtptransceiver/direction) and [`RTCRtpTransceiver.currentDirection`](rtcrtptransceiver/currentdirection)
-   [`RTCRtpReceiver`](rtcrtpreceiver) and [`RTCRtpSender`](rtcrtpsender)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpTransceiverDirection" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpTransceiverDirection</a>
