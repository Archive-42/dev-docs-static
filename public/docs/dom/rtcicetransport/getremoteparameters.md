# RTCIceTransport.getRemoteParameters()

The **[`RTCIceTransport`](../rtcicetransport)** method `getRemoteParameters()` returns an [`RTCIceParameters`](../rtciceparameters) object which provides information uniquely identifying the remote peer for the duration of the ICE session.

The remote peer's parameters are received during ICE signaling and delivered to the transport when the client calls [`RTCPeerConnection.setRemoteDescription()`](../rtcpeerconnection/setremotedescription).

## Syntax

    parameters = RTCIceTransport.getRemoteParameters();

### Parameters

None.

### Return value

An [`RTCIceParameters`](../rtciceparameters) object indicating the [`usernameFragment`](../rtciceparameters/usernamefragment) and [`password`](../rtciceparameters/password) which uniquely identify the remote peer for the duration of the ICE session.

Returns `null` if the parameters haven't been received yet.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcicetransport-getremoteparameters">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceTransport.getRemoteParameters' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`getRemoteParameters`

75

13

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/getRemoteParameters" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/getRemoteParameters</a>
