RTCPeerConnection.addTransceiver()
==================================

The [`RTCPeerConnection`](../rtcpeerconnection) method `addTransceiver()` creates a new [`RTCRtpTransceiver`](../rtcrtptransceiver) and adds it to the set of transceivers associated with the `RTCPeerConnection`. Each transceiver represents a bidirectional stream, with both an [`RTCRtpSender`](../rtcrtpsender) and an [`RTCRtpReceiver`](../rtcrtpreceiver) associated with it.

Syntax
------

    rtpTransceiver = RTCPeerConnection.addTransceiver(trackOrKind, init);

### Parameters

`trackOrKind`  
A [`MediaStreamTrack`](../mediastreamtrack) to associate with the transceiver, or a [`DOMString`](../domstring) which is used as the [`kind`](../mediastreamtrack/kind) of the receiver's [`track`](../rtcrtpreceiver/track), and by extension of the [`RTCRtpReceiver`](../rtcrtpreceiver) itself.

 `init` <span class="badge inline optional">Optional</span>   
An object that conforms to the [`RTCRtpTransceiverInit`](../rtcrtptransceiverinit) dictionary which provides any options that you may wish to specify when creating the new transceiver. Possible values are:

 `direction` <span class="badge inline optional">Optional</span>   
The new transceiver's preferred directionality. This value is used to initialize the new [`RTCRtpTransceiver`](../rtcrtptransceiver) object's [`RTCRtpTransceiver.direction`](../rtcrtptransceiver/direction) property.

 `sendEncodings` <span class="badge inline optional">Optional</span>   
A list of encodings to allow when sending RTP media from the [`RTCRtpSender`](../rtcrtpsender). Each entry is of type [`RTCRtpEncodingParameters`](../rtcrtpencodingparameters).

 `streams` <span class="badge inline optional">Optional</span>   
A list of [`MediaStream`](../mediastream) objects to add to the transceiver's[`RTCRtpReceiver`](../rtcrtpreceiver); when the remote peer's [`RTCPeerConnection`](../rtcpeerconnection)'s `track` event occurs, these are the streams that will be specified by that event.

### Exceptions

`TypeError`  
A string was specified as `trackOrKind` which is not valid. The string must be either `"audio"` or `"video"`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcpeerconnection-addtransceiver">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCPeerConnection.addTransceiver()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`addTransceiver`

69

79

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

-   [WebRTC API](../webrtc_api)
-   [Introduction to the Real-time Transport Protocol (RTP)](../webrtc_api/intro_to_rtp)
-   [`RTCPeerConnection.addTrack()`](addtrack) also creates transceivers
-   [`RTCRtpReceiver`](../rtcrtpreceiver) and [`RTCRtpSender`](../rtcrtpsender)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/addTransceiver" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/addTransceiver</a>
