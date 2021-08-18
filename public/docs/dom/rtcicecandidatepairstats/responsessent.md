# RTCIceCandidatePairStats.responsesSent

The [`RTCIceCandidatePairStats`](../rtcicecandidatepairstats) dictionary's `responsesSent` property indicates the total number of [STUN](https://developer.mozilla.org/en-US/docs/Glossary/STUN) connectivity check responses that have been sent so far on the connection described by this pair of candidates.

## Syntax

    responsesSent = rtcIceCandidatePairStats.responsesSent;

### Value

An integer value indicating the number of times a response has been sent to a [STUN](https://developer.mozilla.org/en-US/docs/Glossary/STUN) connectivity check request.

**Note:** Since it isn't possible to tell the difference between connectivity check requests and consent requests, this value includes both.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcicecandidatepairstats-responsessent">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCIceCandidatePairStats.responsesSent' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`responsesSent`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePairStats/responsesSent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePairStats/responsesSent</a>
