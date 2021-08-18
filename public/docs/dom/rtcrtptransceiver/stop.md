RTCRtpTransceiver.stop()
========================

The `stop()` method in the [`RTCRtpTransceiver`](../rtcrtptransceiver) interface permanently stops the transceiver by stopping both the associated [`RTCRtpSender`](../rtcrtpsender) and [`RTCRtpReceiver`](../rtcrtpreceiver).

**Note:** Until recently, the [`stopped`](stopped) property was provided to return `true` if the connection is stopped. That property has been deprecated and will be removed at some point. Instead, check the value of [`currentDirection`](currentdirection). If it's `stopped`, the transceiver has been stopped.

This method does nothing if the transceiver is already stopped.

Syntax
------

    RTCRtpTransceiver.stop()

### Parameters

None.

### Return value

`undefined`

### Exceptions

`InvalidStateError`  
The `RTCPeerConnection` of which the transceiver is a member is closed.

Usage notes
-----------

When you call `stop()` on a transceiver, the sender immediately stops sending media and each of its RTP streams are closed using the [RTCP](https://developer.mozilla.org/en-US/docs/Glossary/RTCP) `"BYE"` message. The receiver then stops receiving media; the receiver's [`track`](../rtcrtpreceiver/track) is stopped, and the transceiver's [`direction`](direction) is changed to `stopped`, and renegotiation is triggered by sending a `negotiationneeded` event to the `RTCPeerConnection`.

The negotiation process causes [`currentNegotiation`](currentdirection) to be set to `stopped`, finally indicating that the transceiver has been fully stopped.

**Note:** Stopping the transceiver causes a `negotiationneeded` event to be sent to the transceiver's [`RTCPeerConnection`](../rtcpeerconnection), so the connection can adapt to the change.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcrtptransceiver-stop">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCRtpTransceiver.stop()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`stop`

88

88

59

No

No

11

88

88

59

No

11

No

See also
--------

-   [WebRTC API](../webrtc_api)
-   [Introduction to the Real-time Transport Protocol (RTP)](../webrtc_api/intro_to_rtp)
-   [`MediaStreamTrack`](../mediastreamtrack)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpTransceiver/stop" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpTransceiver/stop</a>
