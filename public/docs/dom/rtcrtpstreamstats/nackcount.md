RTCRtpStreamStats.nackCount
===========================

The `nackCount` property of the [`RTCRtpStreamStats`](../rtcrtpstreamstats) dictionary is a numeric value indicating the number of times the receiver sent a **NACK packet** to the sender. A NACK (Negative ACKnowledgement, also called "Generic NACK") packet tells the sender that one or more of the [RTP](https://developer.mozilla.org/en-US/docs/Glossary/RTP) packets it sent were lost in transport.

Syntax
------

    var nackCount = RTCRtpStreamStats.nackCount;

### Value

An integer value indicating how many times the receiver sent a NACK packet to the sender after detecting that one or more packets were lost during transport.

**Note:** This value is only available on the receiver.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcinboundrtpstreamstats-nackcount">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCInboundRtpStreamStats: nackCount' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcoutboundrtpstreamstats-nackcount">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCOutboundRtpStreamStats: nackCount' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`nackCount`

No

No

55

No

No

?

No

No

55

No

?

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpStreamStats/nackCount" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpStreamStats/nackCount</a>
