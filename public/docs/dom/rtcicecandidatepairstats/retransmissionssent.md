# RTCIceCandidatePairStats.retransmissionsSent

The [`RTCIceCandidatePairStats`](../rtcicecandidatepairstats) dictionary's `retransmissionsSent` property indicates the total number of [STUN](https://developer.mozilla.org/en-US/docs/Glossary/STUN) connectivity check request retransmissions that have been sent so far on the pair of candidates.

The number of retransmissions that have been received on the connection can be found in [`retransmissionsReceived`](retransmissionsreceived).

## Syntax

    retransmissionsSent = rtcIceCandidatePairStats.retransmissionsSent;

### Value

An integer value indicating the total number of retransmitted STUN connectivity check requests have been sent on the connection referenced by this candidate pair so far.

**Note:** Retransmissions are connectivity check requests with a `TRANSACTION_TRANSMIT_COUNTER` attribute whose `req` field is greater than 1 (indicating that the request has been transmitted more than once). See [RFC 7982](https://tools.ietf.org/html/rfc7982) for further details.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcicecandidatepairstats-retransmissionssent">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCIceCandidatePairStats.retransmissionsSent' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`retransmissionsSent`

No

No

No

No

?

?

No

No

No

?

?

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePairStats/retransmissionsSent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePairStats/retransmissionsSent</a>
