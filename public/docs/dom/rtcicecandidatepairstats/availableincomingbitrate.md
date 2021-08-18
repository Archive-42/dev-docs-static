# RTCIceCandidatePairStats.availableIncomingBitrate

The [`RTCIceCandidatePairStats`](../rtcicecandidatepairstats) property `availableIncomingBitrate` returns a value indicative of the available inbound capacity of the network connection represented by the candidate pair. The higher the value, the more bandwidth you can assume is available for incoming data.

You can get the incoming outgoing bitrate from [`availableoutgoingBitrate`](availableoutgoingbitrate).

## Syntax

    availableIncomingBitrate = rtcIceCandidatePairStats.availableIncomingBitrate;

### Value

A floating-point value which approximates the amount of available bandwidth for incoming data on the network connection described by the `RTCIceCandidatePair`. The value is reported in bits per second and is computed over a 1-second interval.

The value returned is calculated by adding up the available bit rate for every [RTP](https://developer.mozilla.org/en-US/docs/Glossary/RTP) stream using the connection described by this candidate pair. The returned value doesn't take into account overhead introduced by underlying protocols, including IP, UDP, or TCP.

**Note:** The returned value is computed using a method similar—but not identical—to the Transport Independent Application Specific Maximum (TIAS) described in [RFC 3890: 6.2](https://tools.ietf.org/html/rfc3890).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcicecandidatepairstats-availableincomingbitrate">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCIceCandidatePairStats.availableIncomingBitrate' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`availableIncomingBitrate`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePairStats/availableIncomingBitrate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePairStats/availableIncomingBitrate</a>
