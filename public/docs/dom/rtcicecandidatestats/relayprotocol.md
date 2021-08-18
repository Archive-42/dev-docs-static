# RTCIceCandidateStats.relayProtocol

The [`RTCIceCandidateStats`](../rtcicecandidatestats) dictionary's `relayProtocol` property specifies the protocol being used by a local [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) candidate to communicate with the [TURN](https://developer.mozilla.org/en-US/docs/Glossary/TURN) server.

The ICE protocl being used by the candidate otherwise can be obtained from the [`protocol`](protocol) property.

## Syntax

    relayProtocol = rtcIceCandidateStats.relayProtocol;

### Value

A [`DOMString`](../domstring) identifying the protocol being used by the endpoint to communicate with the TURN server. The possible values are:

`tcp`  
TCP (Transport Control Protocol) is being used to communicate with the TURN server.

`tls`  
TLS (Transport Layer Security) is being used to communicate with the TURN server.

`udp`  
UDP (User Datagram Protocol) is being used to communicate with the TURN server.

**Note:** This property is only present on [`RTCIceCandidateStats`](../rtcicecandidatestats) objects that represent local candidates.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcicecandidatestats-relayprotocol">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCIceCandidateStats.relayProtocol' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`relayProtocol`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidateStats/relayProtocol" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidateStats/relayProtocol</a>
