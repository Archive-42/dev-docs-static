RTCRtpReceiver.transport
========================

The read-only `transport` property of an [`RTCRtpReceiver`](../rtcrtpreceiver) object provides the [`RTCDtlsTransport`](../rtcdtlstransport) object used to interact with the underlying transport over which the receiver is exchanging Real-time Transport Control Protocol ([RTCP](https://developer.mozilla.org/en-US/docs/Glossary/RTCP)) packets.

This transport is responsible for receiving the data for the media on the receiver's [`track`](track).

Syntax
------

    let transport = rtcRtpReceiver.transport;

### Value

An [`RTCDtlsTransport`](../rtcdtlstransport) object representing the underlying transport being used by the receiver to exchange packets with the remote peer, or `null` if the receiver isn't yet connected to a transport.

Description
-----------

When the `RTCRtpReceiver` is first created, the value of `transport` is `null`. This is replaced with an `RTCDtlsTransport` once the receiver's transport has been established.

Note that when bundling is in effect—that is, when the [`RTCPeerConnection`](../rtcpeerconnection) was created with an [`RTCConfiguration`](../rtcconfiguration) object whose [`bundlePolicy`](../rtcconfiguration/bundlepolicy) is `max-compat` or `max-bundle`—multiple receivers may be sharing the same transport; in this case, all of them are using the same connection to transmit and/or receive [RTP](https://developer.mozilla.org/en-US/docs/Glossary/RTP) and [RTCP](https://developer.mozilla.org/en-US/docs/Glossary/RTCP) packets.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcrtpreceiver-transport">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCRtpReceiver.transport' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

59

12

Yes

No

46

No

59

59

Yes

43

No

7.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpReceiver/transport" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpReceiver/transport</a>
