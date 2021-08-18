RTCOutboundRtpStreamStats.lastPacketSentTimestamp
=================================================

The `lastPacketSentTimestamp` property of the [`RTCOutboundRtpStreamStats`](../rtcoutboundrtpstreamstats) dictionary indicates the time at which the [`RTCRtpSender`](../rtcrtpsender) described by this [`RTCOutboundRtpStreamStats`](../rtcoutboundrtpstreamstats) object last transmitted a packet to the remote receiver.

Syntax
------

    var lastPacketTimestamp = RTCOutboundRtpStreamStats.lastPacketSentTimestamp;

### Value

A [`DOMHighResTimeStamp`](../domhighrestimestamp) which specifies the time at which the most recently received packet arrived on this RTP stream.

**Note:** This value differs from the [`timestamp`](../rtcstats/timestamp), which represents the time at which the statistics object was created.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-RTCOutboundRtpStreamStats-lastpacketsenttimestamp">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCOutboundRtpStreamStats.lastPacketSentTimestamp' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.RTCOutboundRtpStreamStats.lastPacketSentTimestamp`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCOutboundRtpStreamStats/lastPacketSentTimestamp" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCOutboundRtpStreamStats/lastPacketSentTimestamp</a>
