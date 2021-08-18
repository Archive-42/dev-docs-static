RTCRtpTransceiverInit
=====================

The `RTCRtpTransceiverInit` dictionary is used when calling the WebRTC function [`RTCPeerConnection.addTransceiver()`](rtcpeerconnection/addtransceiver) to provide configuration options for the new transceiver.

Properties
----------

 `direction` <span class="badge inline optional">Optional</span>   
The new transceiver's preferred directionality. This value is used to initialize the new [`RTCRtpTransceiver`](rtcrtptransceiver) object's [`RTCRtpTransceiver.direction`](rtcrtptransceiver/direction) property.

 `sendEncodings` <span class="badge inline optional">Optional</span>   
A list of encodings to allow when sending RTP media from the [`RTCRtpSender`](rtcrtpsender). Each entry is of type [`RTCRtpEncodingParameters`](rtcrtpencodingparameters).

 `streams` <span class="badge inline optional">Optional</span>   
A list of [`MediaStream`](mediastream) objects to add to the transceiver's[`RTCRtpReceiver`](rtcrtpreceiver); when the remote peer's [`RTCPeerConnection`](rtcpeerconnection)'s `track` event occurs, these are the streams that will be specified by that event.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcrtptransceiverinit">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCRtpTransceiverInit' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`RTCRtpTransceiverInit`

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

`direction`

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

`sendEncodings`

69

≤18

No

`sendEncodings` is not yet implemented in Firefox. See [bug 1396918](https://bugzil.la/1396918).

No

?

?

69

69

No

`sendEncodings` is not yet implemented in Firefox. See [bug 1396918](https://bugzil.la/1396918).

?

?

10.0

`streams`

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
-   [`RTCPeerConnection.addTransceiver()`](rtcpeerconnection/addtransceiver)
-   [`RTCRtpTransceiver`](rtcrtptransceiver)
-   [`RTCRtpReceiver`](rtcrtpreceiver) and [`RTCRtpSender`](rtcrtpsender)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpTransceiverInit" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpTransceiverInit</a>
