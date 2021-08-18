RTCInboundRtpStreamStats.lastPacketReceivedTimestamp
====================================================

The `lastPacketReceivedTimestamp` property of the [`RTCInboundRtpStreamStats`](../rtcinboundrtpstreamstats) dictionary indicates the time at which the most recently received packet arrived from this source.

Syntax
------

    var lastPacketTimestamp = rtcInboundRtpStreamStats.lastPacketReceivedTimestamp;

### Value

A [`DOMHighResTimeStamp`](../domhighrestimestamp) which specifies the time at which the most recently received packet arrived on this RTP stream.

**Note:** This value differs from the [`timestamp`](../rtcstats/timestamp), which represents the time at which the statistics object was created.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcinboundrtpstreamstats-lastpacketreceivedtimestamp">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCInboundRtpStreamStats.lastPacketReceivedTimestamp' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.RTCInboundRtpStreamStats.lastPacketReceivedTimestamp`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCInboundRtpStreamStats/lastPacketReceivedTimestamp" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCInboundRtpStreamStats/lastPacketReceivedTimestamp</a>
