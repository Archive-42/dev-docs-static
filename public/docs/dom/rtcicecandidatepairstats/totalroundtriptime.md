RTCIceCandidatePairStats.totalRoundTripTime
===========================================

The [`RTCIceCandidatePairStats`](../rtcicecandidatepairstats) dictionary's `totalRoundTripTime` property is the total time that has elapsed between sending [STUN](https://developer.mozilla.org/en-US/docs/Glossary/STUN) requests and receiving the responses, for all such requests that have been made so far on the pair of candidates described by this `RTCIceCandidatePairStats` object. This value includes both connectivity check and consent check requests.

Syntax
------

    totalRTT = rtcIceCandidatePairStats.totalRoundTripTime;

### Value

This floating-point value indicates the total number of seconds which have elapsed between sending out STUN connectivity and consent check requests and receiving their responses, for all such requests made so far on the connection described by this candidate pair.

You can calculate the average round-trip time (RTT) by dividing this value by the value of the [`responsesReceived`](responsesreceived) property:

    rtt = rtcIceCandidatePairStats.totalRoundTripTime /
            rtcIceCandidatePairStats.responsesReceived;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcicecandidatepairstats-totalroundtriptime">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCIceCandidatePairStats.totalRoundTripTime' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`totalRoundTripTime`

71

Yes

≤79

≤79

No

No

?

?

No

71

Yes

No

?

?

10.0

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePairStats/totalRoundTripTime" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePairStats/totalRoundTripTime</a>
