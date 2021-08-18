RTCIceCandidateType
===================

The [WebRTC API's](webrtc_api) `RTCIceCandidateType` enumerated type provides a set of [`DOMString`](domstring) values representing the types of [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) candidate that can arrive. These strings are taken directly from the `candidate` a-line in [SDP](https://developer.mozilla.org/en-US/docs/Glossary/SDP).

Values
------

These candidate types are listed in order of priority; the higher in the list they are, the more efficient they are.

`host`  
The candidate is a host candidate, whose IP address as specified in the [`RTCIceCandidate.ip`](rtcicecandidate/address) property is in fact the true address of the remote peer.

`srflx`  
The candidate is a server reflexive candidate; the `ip` indicates an intermediary address assigned by the [STUN](https://developer.mozilla.org/en-US/docs/Glossary/STUN) server to represent the candidate's peer anonymously.

`prflx`  
The candidate is a peer reflexive candidate; the `ip` is an intermediary address assigned by the STUN server to represent the candidate's peer anonymously.

`relay`  
The candidate is a relay candidate, obtained from a [TURN](https://developer.mozilla.org/en-US/docs/Glossary/TURN) server. The relay candidate's IP address is an address the TURN server uses to forward the media between the two peers.

Usage notes
-----------

The `RTCIceCandidateType` enumeration is used by the [`type`](rtcicecandidate/type) property of [`RTCIceCandidate`](rtcicecandidate) objects, as well as when reporting statistics on candidates using [`RTCIceCandidateStats.candidateType`](rtcicecandidatestats/candidatetype).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcicecandidatetype">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceCandidateType' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`RTCIceCandidateType`

No

An `RTCIceCandidate` object's `type` is not maintained by this browser.

No

An `RTCIceCandidate` object's `type` is not maintained by this browser.

No

An `RTCIceCandidate` object's `type` is not maintained by this browser.

No

?

?

No

An `RTCIceCandidate` object's `type` is not maintained by this browser.

No

An `RTCIceCandidate` object's `type` is not maintained by this browser.

No

An `RTCIceCandidate` object's `type` is not maintained by this browser.

?

?

No

An `RTCIceCandidate` object's `type` is not maintained by this browser.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidateType" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidateType</a>
