RTCPeerConnection.getReceivers()
================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `RTCPeerConnection.getReceivers()` method returns an array of [`RTCRtpReceiver`](../rtcrtpreceiver) objects, each of which represents one RTP receiver. Each RTP receiver manages the reception and decoding of data for a [`MediaStreamTrack`](../mediastreamtrack) on an [`RTCPeerConnection`](../rtcpeerconnection)

Syntax
------

    var receivers = rtcPeerConnection.getReceivers();

### Return value

An array of [`RTCRtpReceiver`](../rtcrtpreceiver) objects, one for each track on the connection. The array is empty if there are no RTP receivers on the connection.

The order of the returned `RTCRtpReceiver` instances is not defined by the specification, and may change from one call to `getReceivers()` to the next.

Example
-------

tbd

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-peerconnection-getreceivers">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCPeerConnection.getReceivers()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`getReceivers`

59

79

22

No

46

11

59

59

44

43

11

6.0

See also
--------

-   [WebRTC](https://developer.mozilla.org/en-US/docs/Web/Guide/API/WebRTC_API)
-   [`RTCRtpSender`](../rtcrtpsender)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/getReceivers" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/getReceivers</a>
