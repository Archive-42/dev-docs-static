RTCIceCandidate.sdpMLineIndex
=============================

The read-only `sdpMLineIndex` property on the [`RTCIceCandidate`](../rtcicecandidate) interface is a zero-based index of the m-line describing the media associated with the candidate.

This value is specified when creating the [`RTCIceCandidate`](../rtcicecandidate) by setting the corresponding [`sdpMLineIndex`](../rtcicecandidateinit/sdpmlineindex) value in the [`RTCIceCandidateInit`](../rtcicecandidateinit) object when creating a new candidate with [`new RTCIceCandidate()`](rtcicecandidate).

If you instead call `RTCIceCandidate()` with a string parameter containing the `candidate` m-line text, the value of `sdpMLineIndex` is extracted from the m-line.

Syntax
------

    var sdpMLineIndex = RTCIceCandidate.sdpMLineIndex;

### Value

A number containing a 0-based index into the set of m-lines providing media descriptions, indicating which media source is associated with the candidate, or `null` if no such association is available.

**Note:** Attempting to add a candidate (using [`addIceCandidate()`](../rtcpeerconnection/addicecandidate)) that has a value of `null` for either `sdpMid` or `sdpMLineIndex` will throw a `TypeError` exception.

Example
-------

...

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcicecandidate-sdpmlineindex">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceCandidate.sdpMLineIndex' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

23

15

22

No

15

11

≤37

25

Yes

14

11

1.5

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/sdpMLineIndex" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/sdpMLineIndex</a>
