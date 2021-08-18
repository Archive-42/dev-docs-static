# RTCIceCandidateStats.protocol

The [`RTCIceCandidateStats`](../rtcicecandidatestats) dictionary's `protocol` property specifies the protocol the specified candidate would use for communication with the remote peer.

## Syntax

    protocol = rtcIceCandidateStats.protocol;

### Value

The value is one of the members of the [`RTCIceProtocol`](../rtciceprotocol) enumerated string type:

`tcp`  
The candidate, if selected, would use [TCP](https://developer.mozilla.org/en-US/docs/Glossary/TCP) as the transport protocol for its data. The [`tcpType`](../rtcicecandidate/tcptype) property provides additional information about the kind of TCP candidate represented by the object.

`udp`  
The candidate will use the [UDP](https://developer.mozilla.org/en-US/docs/Glossary/UDP) transport protocol for its data. This is the preferred protocol for media interactions because of its better performance profile.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcicecandidatestats-protocol">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCIceCandidateStats.protocol' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`protocol`

No

No

64

31

No

?

?

No

No

64

31

?

?

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidateStats/protocol" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidateStats/protocol</a>
