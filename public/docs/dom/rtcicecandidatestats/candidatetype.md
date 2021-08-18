# RTCIceCandidateStats.candidateType

The [`RTCIceCandidateStats`](../rtcicecandidatestats) interface's `candidateType` property is a string which indicates the type of [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) candidate the object represents.

## Syntax

    candidateType = rtcIceCandidateStats.candidateType;

### Value

A [`DOMString`](../domstring) whose value is one of the strings found in the [`RTCIceCandidateType`](../rtcicecandidatetype) enumerated type:

`host`  
The candidate is a host candidate, whose IP address as specified in the [`RTCIceCandidate.ip`](../rtcicecandidate/address) property is in fact the true address of the remote peer.

`srflx`  
The candidate is a server reflexive candidate; the `ip` indicates an intermediary address assigned by the [STUN](https://developer.mozilla.org/en-US/docs/Glossary/STUN) server to represent the candidate's peer anonymously.

`prflx`  
The candidate is a peer reflexive candidate; the `ip` is an intermediary address assigned by the STUN server to represent the candidate's peer anonymously.

`relay`  
The candidate is a relay candidate, obtained from a [TURN](https://developer.mozilla.org/en-US/docs/Glossary/TURN) server. The relay candidate's IP address is an address the TURN server uses to forward the media between the two peers.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcicecandidatestats">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCIceCandidateStats.candidateType' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`candidateType`

No

No

27

No

?

?

No

No

27

?

?

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidateStats/candidateType" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidateStats/candidateType</a>
