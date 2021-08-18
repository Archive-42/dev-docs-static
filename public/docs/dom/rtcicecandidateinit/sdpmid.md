# RTCIceCandidateInit.sdpMid

The optional property `sdpMid` in the **[`RTCIceCandidateInit`](../rtcicecandidateinit)** dictionary specifies the value of the [`RTCIceCandidate`](../rtcicecandidate) object's [`sdpMid`](../rtcicecandidate/sdpmid) property.

## Value

A [`DOMString`](../domstring) which uniquely identifies the source media component from which the candidate draws data, or `null` if no such association exists for the candidate.

**Note:** Attempting to add a candidate (using [`addIceCandidate()`](../rtcpeerconnection/addicecandidate)) that has a value of `null` for either `sdpMid` or `sdpMLineIndex` will throw a `TypeError` exception.

## Example

...

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcicecandidateinit-sdpmid">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceCandidateInit.sdpMid' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`sdpMid`

Yes

≤18

22

No

Yes

?

Yes

Yes

Yes

Yes

?

Yes

## See also

- [WebRTC API](../webrtc_api)
- [`RTCIceCandidate.sdpMid`](../rtcicecandidate/sdpmid)
- [`RTCPeerConnection.addIceCandidate()`](../rtcpeerconnection/addicecandidate)
- `icecandidate`
- [Lifetime of a WebRTC session](../webrtc_api/session_lifetime)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidateInit/sdpMid" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidateInit/sdpMid</a>
