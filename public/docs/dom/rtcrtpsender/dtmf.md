RTCRtpSender.dtmf
=================

The read-only `dtmf` property on the **[`RTCRtpSender`](../rtcrtpsender)** interface returns a [`RTCDTMFSender`](../rtcdtmfsender) object which can be used to send [DTMF](https://developer.mozilla.org/en-US/docs/Glossary/DTMF) tones over the [`RTCPeerConnection`](../rtcpeerconnection) . See [Using DTMF](../webrtc_api/using_dtmf) for details on how to make use of th`e` returned `RTCDTMFSender` object.

Syntax
------

    var dtmfSender = RTCRtpSender.dtmf;

### Value

An [`RTCDTMFSender`](../rtcdtmfsender) which can be used to send DTMF over the RTP session, or `null` if the track being carried by the RTP session or the [`RTCPeerConnection`](../rtcpeerconnection) as a whole doesn't support DTMF.

Only audio tracks can support DTMF, and typically only one audio track per `RTCPeerConnection` will have an associated [`RTCDTMFSender`](../rtcdtmfsender)

Example
-------

tbd

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcrtpsender-dtmf">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCRtpSender.dtmf' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`dtmf`

66

≤18

52

No

53

13.1

66

66

52

47

13.4

9.0

See also
--------

-   [WebRTC API](../webrtc_api)
-   [Using DTMF with WebRTC](../webrtc_api/using_dtmf)
-   [`RTCPeerConnection`](../rtcpeerconnection)
-   [`RTCDTMFSender`](../rtcdtmfsender)
-   [`RTCRtpSender`](../rtcrtpsender)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSender/dtmf" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSender/dtmf</a>
