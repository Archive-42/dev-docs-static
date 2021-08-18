RTCIceCandidatePairStats.availableOutgoingBitrate
=================================================

The [`RTCIceCandidatePairStats`](../rtcicecandidatepairstats) property `availableOutgoingBitrate` returns a value indicative of the available outbound capacity of the network connection represented by the candidate pair. The higher the value, the more bandwidth you can assume is available for outgoing data.

You can get the incoming available bitrate from [`availableIncomingBitrate`](availableincomingbitrate).

Syntax
------

    availableOutgoingBitrate = rtcIceCandidatePairStats.availableOutgoingBitrate;

### Value

A floating-point value which approximates the amount of available bandwidth for outgoing data on the network connection described by the `RTCIceCandidatePair`. The value is reported in bits per second and is computed over a 1-second interval.

The returned value is `undefined` in each of the following situations:

-   The underlying implementation doesn't support computing a sender-side estimate of the outgoing bit rate.
-   The [`RTCIceCandidatePair`](../rtcicecandidatepair) described by this object has never been used.
-   The candidate pair was once in use, but no longer is.

The value returned is calculated by adding up the available bit rate for every [RTP](https://developer.mozilla.org/en-US/docs/Glossary/RTP) stream using the connection described by this candidate pair. The returned value doesn't take into account overhead introduced by underlying protocols, including IP, UDP, or TCP.

**Note:** The returned value is computed using a method similar—but not identical—to the Transport Independent Application Specific Maximum (TIAS) described in [RFC 3890: 6.2](https://tools.ietf.org/html/rfc3890).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcicecandidatepairstats-availableoutgoingbitrate">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCIceCandidatePairStats.availableoutgoingbitrate' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`availableOutgoingBitrate`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePairStats/availableOutgoingBitrate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePairStats/availableOutgoingBitrate</a>
