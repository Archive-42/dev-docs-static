# RTCIceCandidate.sdpMid

The read-only property `sdpMid` on the [`RTCIceCandidate`](../rtcicecandidate) interface returns a [`DOMString`](../domstring) specifying the media stream identification tag of the media component with which the candidate is associated. This ID uniquely identifies a given stream for the component with which the candidate is associated.

This property can be configured by specifying the value of the [`sdpMid`](../rtcicecandidateinit/sdpmid) property when constructing the new candidate object using [`RTCIceCandidate()`](rtcicecandidate). If you call the constructor with an m-line string instead of an `RTCIceCandidateInit` object, the value of `sdpMid` is extracted from the specified candidate m-line string.

## Syntax

    var sdpMid = RTCIceCandidate.sdpMid;

### Value

A [`DOMString`](../domstring) which uniquely identifies the source media component from which the candidate draws data, or `null` if no such association exists for the candidate.

**Note:** Attempting to add a candidate (using [`addIceCandidate()`](../rtcpeerconnection/addicecandidate)) that has a value of `null` for either `sdpMid` or `sdpMLineIndex` will throw a `TypeError` exception.

## Example

...

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcicecandidate-sdpmid">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceCandidate.sdpMid' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/sdpMid" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/sdpMid</a>
