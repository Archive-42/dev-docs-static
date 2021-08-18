# RTCIceCandidateStats.localCandidateId

The [`RTCIceCandidatePairStats`](../rtcicecandidatepairstats) property `localCandidateId` is a string that uniquely identifies the local [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) candidate which was analyzed to generate the [`RTCIceCandidateStats`](../rtcicecandidatestats) used to compute the statistics for this pair of candidates.

## Syntax

    localCandidateId = rtcIceCandidatePairStats.localCandidateId;

### Value

A [`DOMString`](../domstring) giving a unique identifier for the local [`RTCIceCandidate`](../rtcicecandidate) for the connection described by this `RTCIceCandidatePairStats` object.

This candidate is the source of one of the two [`RTCIceCandidateStats`](../rtcicecandidatestats) objects that were used to compute the contents of this [`RTCIceCandidatePairStats`](../rtcicecandidatepairstats) object.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcicecandidatepairstats-localcandidateid">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCIceCandidatePairStats.localCandidateId' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`localCandidateId`

No

No

29

No

?

?

No

No

29

?

?

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePairStats/localCandidateId" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePairStats/localCandidateId</a>
