RTCIceCandidatePairStats.lastRequestTimestamp
=============================================

The [`RTCIceCandidatePairStats`](../rtcicecandidatepairstats) property `lastRequestTimestamp` indicates the time at which the most recent [STUN](https://developer.mozilla.org/en-US/docs/Glossary/STUN) request was sent on the described candidate pair.

Syntax
------

    lastRequestTimestamp = rtcIceCandidatePairStats.lastRequestTimestamp;

### Value

A [`DOMHighResTimeStamp`](../domhighrestimestamp) object indicating the timestamp at which the last (most recent) STUN request was sent on the connection indicated by the described pair of candidates.

You can use this value in combination with [`firstRequestTimestamp`](firstrequesttimestamp) and [`requestsSent`](requestssent) to compute the average interval between consecutive connectivity checks:

    avgCheckInterval = (candidatePairStats.lastRequestTimestamp -
                        candidatePairStats.firstRequestTimestamp) /
                       candidatePairStats.requestsSent;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcicecandidatepairstats-lastrequesttimestamp">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCIceCandidatePairStats.lastRequestTimestamp' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`lastRequestTimestamp`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePairStats/lastRequestTimestamp" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePairStats/lastRequestTimestamp</a>
