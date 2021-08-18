RTCOutboundRtpStreamStats.nackCount
===================================

The `nackCount` property of the [`RTCOutboundRtpStreamStats`](../rtcoutboundrtpstreamstats) dictionary is a numeric value indicating the number of times the [`RTCRtpSender`](../rtcrtpsender) described by this object received a **NACK** packet from the remote receiver. A NACK (Negative ACKnowledgement, also called "Generic NACK") packet is used by the [`RTCRtpReceiver`](../rtcrtpreceiver) to inform the sender that one or more [RTP](https://developer.mozilla.org/en-US/docs/Glossary/RTP) packets it sent were lost in transport.

Syntax
------

    var nackCount = RTCOutboundRtpStreamStats.nackCount;

### Value

An integer value indicating how many times the sender received a NACK packet from the receiver, indicating the loss of one or more packets.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-RTCOutboundRtpStreamStats-nackcount">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCOutboundRtpStreamStats.nackCount' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.RTCOutboundRtpStreamStats.nackCount`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCOutboundRtpStreamStats/nackCount" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCOutboundRtpStreamStats/nackCount</a>
