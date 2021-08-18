RTCRtpSender.transport
======================

The read-only `transport` property of an [`RTCRtpSender`](../rtcrtpsender) object provides the [`RTCDtlsTransport`](../rtcdtlstransport) object used to interact with the underlying transport over which the sender is exchanging Real-time Transport Control Protocol ([RTCP](https://developer.mozilla.org/en-US/docs/Glossary/RTCP)) packets.

This transport is responsible for receiving the data for the media on the sender's [`track`](../rtcrtpreceiver/track).

Syntax
------

    let transport = rtcRtpSender.transport;

### Value

An [`RTCDtlsTransport`](../rtcdtlstransport) object representing the underlying transport being used by the sender to exchange packets with the remote peer, or `null` if the sender isn't yet connected to a transport.

Description
-----------

When the `RTCRtpSender` is first created, the value of `transport` is `null`. This is replaced with an `RTCDtlsTransport` once the sender's transport has been established.

Note that when bundling is in effect—that is, when the [`RTCPeerConnection`](../rtcpeerconnection) was created with an [`RTCConfiguration`](../rtcconfiguration) object whose [`bundlePolicy`](../rtcconfiguration/bundlepolicy) is `max-compat` or `max-bundle`—multiple senders may be sharing the same transport; in this case, all of them are using the same connection to transmit and/or receive [RTP](https://developer.mozilla.org/en-US/docs/Glossary/RTP) and [RTCP](https://developer.mozilla.org/en-US/docs/Glossary/RTCP) packets.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcrtpsender-transport">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCRtpSender.transport' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`transport`

75

12-79

34

No

62

No

75

75

34

54

No

11.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSender/transport" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSender/transport</a>
