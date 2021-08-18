# RTCIceCandidatePairStats.requestsSent

The [`RTCIceCandidatePairStats`](../rtcicecandidatepairstats) dictionary's `requestsSent` property indicates the total number of [STUN](https://developer.mozilla.org/en-US/docs/Glossary/STUN) connectivity check requests that have been sent so far on the connection described by this pair of candidates.

## Syntax

    requestsSent = rtcIceCandidatePairStats.requestsSent;

### Value

An integer value which specifies the number of STUN connectivity requests that have been sent to date on the connection described by this pair of [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) candidates.

**Note:** The reported number of requests _does not_ include retransmissions. If a request had to be repeated due to network issues, it will be counted multiple times here. This differs from [`requestsReceived`](requestsreceived), which _does_ include retransmisions.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcicecandidatepairstats-requestssent">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCIceCandidatePairStats.requestsSent' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`requestsSent`

Yes

≤79

No

No

?

?

Yes

Yes

No

?

?

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePairStats/requestsSent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePairStats/requestsSent</a>
