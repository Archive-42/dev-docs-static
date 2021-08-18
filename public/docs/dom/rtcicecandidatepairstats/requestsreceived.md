RTCIceCandidatePairStats.requestsReceived
=========================================

The [`RTCIceCandidatePairStats`](../rtcicecandidatepairstats) dictionary's `requestsReceived` property indicates the total number of [STUN](https://developer.mozilla.org/en-US/docs/Glossary/STUN) connectivity check requests that have been received so far on the connection described by this pairing of candidates.

Syntax
------

    requestsReceived = rtcIceCandidatePairStats.requestsReceived;

### Value

An integer value which specifies the number of STUN connectivity and/or consent requests that have been received to date on the connection described by this pair of [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) candidates.

Because there's no way to tell the difference between requests made to check connectivity and requests made to check consent, the returned figure includes both.

**Note:** The reported number of requests includes retransmissions. If a request had to be repeated due to network issues, it will be counted multiple times here. This differs from [`requestsSent`](requestssent), which *does not* include retransmisions.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcicecandidatepairstats-requestsreceived">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCIceCandidatePairStats.requestsReceived' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`requestsReceived`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePairStats/requestsReceived" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePairStats/requestsReceived</a>
