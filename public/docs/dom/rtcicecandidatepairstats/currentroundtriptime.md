RTCIceCandidatePairStats.currentRoundTripTime
=============================================

The [`RTCIceCandidatePairStats`](../rtcicecandidatepairstats) property `currentRoundTripTime` is a floating-point value indicating the number of seconds it takes for data to be sent by this peer to the remote peer and back over the connection described by this pair of [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) candidates.

Syntax
------

    rtt = rtcIceCandidatePairStats.currentRoundTripTime;

### Value

A floating-point value indicating the round-trip time, in seconds for the connection described by the pair of candidates for which this `RTCIceCandidatePairStats` object offers statistics.

This value is computed by observing the time that elapsed between the most recent [STUN](https://developer.mozilla.org/en-US/docs/Glossary/STUN) request being sent to the remote peer and the response to that request arriving. This information may come from ongoing STUN connectivity checks as well as from consent requests made when the connection was initially being opened.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcicecandidatepairstats-currentroundtriptime">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCIceCandidatePairStats.currentRoundTripTime' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`currentRoundTripTime`

71

Yes

≤79

≤79

No

No

?

?

71

Yes

71

Yes

No

?

?

10.0

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePairStats/currentRoundTripTime" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePairStats/currentRoundTripTime</a>
