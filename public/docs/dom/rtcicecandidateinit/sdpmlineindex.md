RTCIceCandidateInit.sdpMLineIndex
=================================

The optional property `sdpMLineIndex` in the **[`RTCIceCandidateInit`](../rtcicecandidateinit)** dictionary specifies the value of the [`RTCIceCandidate`](../rtcicecandidate) object's [`sdpMLineIndex`](../rtcicecandidate/sdpmlineindex) property.

Value
-----

A number containing a 0-based index into the set of m-lines providing media descriptions, indicating which media source is associated with the candidate, or `null` if no such association is available.

**Note:** Attempting to add a candidate (using [`addIceCandidate()`](../rtcpeerconnection/addicecandidate)) that has a value of `null` for either `sdpMid` or `sdpMLineIndex` will throw a `TypeError` exception.

Example
-------

...

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcicecandidateinit-sdpmlineindex">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceCandidateInit.sdpMLineIndex' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`sdpMLineIndex`

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

See also
--------

-   [WebRTC API](../webrtc_api)
-   [`RTCIceCandidate.sdpMLineIndex`](../rtcicecandidate/sdpmlineindex)
-   [`RTCPeerConnection.addIceCandidate()`](../rtcpeerconnection/addicecandidate)
-   `icecandidate`
-   [Lifetime of a WebRTC session](../webrtc_api/session_lifetime)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidateInit/sdpMLineIndex" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidateInit/sdpMLineIndex</a>
