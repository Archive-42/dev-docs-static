# RTCIceTransport.getLocalParameters()

The **[`RTCIceTransport`](../rtcicetransport)** method `getLocalParameters()` returns an [`RTCIceParameters`](../rtciceparameters) object which provides information uniquely identifying the local peer for the duration of the ICE session.

The local peer's parameters are obtained during ICE signaling and delivered to the transport when the client calls [`RTCPeerConnection.setLocalDescription()`](../rtcpeerconnection/setlocaldescription).

## Syntax

    parameters = RTCIceTransport.getLocalParameters();

### Parameters

None.

### Return value

An [`RTCIceParameters`](../rtciceparameters) object indicating the [`usernameFragment`](../rtciceparameters/usernamefragment) and [`password`](../rtciceparameters/password) which uniquely identify the local peer for the duration of the ICE session.

Returns `null` if the parameters have not yet been received.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcicetransport-getlocalparameters">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceTransport.getLocalParameters' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

## Browser compatibility

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

`getLocalParameters`

75

79

No

No

62

No

75

75

No

54

No

11.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/getLocalParameters" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/getLocalParameters</a>
