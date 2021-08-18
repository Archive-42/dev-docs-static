RTCIceCandidatePairStats.consentExpiredTimestamp
================================================

The [`RTCIceCandidatePairStats`](../rtcicecandidatepairstats) property `consentExpiredTimestamp` indicates the time at which the most recent [STUN](https://developer.mozilla.org/en-US/docs/Glossary/STUN) binding response expired. This indicates when the current STUN bindings — the mapping of the IP address and port configurations for both peers on the [WebRTC](https://developer.mozilla.org/en-US/docs/Glossary/WebRTC) connection — are due to expire. If this time has arrived or passed, the bindings have expired.

Syntax
------

    consentExpiration = rtcIceCandidatePairStats.consentExpiredTimestamp;

### Value

A [`DOMHighResTimeStamp`](../domhighrestimestamp) object that indicates the time at which the STUN binding that allows the two peers described by this [`RTCIceCandidatePair`](../rtcicecandidatepair) to communicate will expire (or the time at which the binding did expire, if the time has passed).

This property's value is `undefined` if there have been no STUN binding responses yet on the candidate pair. This is only possible if <span class="page-not-created">`responsesReceived`</span> is 0.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcicecandidatepairstats-consentexpiredtimestamp">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCIceCandidatePairStats.consentExpiredTimestamp' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`consentExpiredTimestamp`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePairStats/consentExpiredTimestamp" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePairStats/consentExpiredTimestamp</a>
