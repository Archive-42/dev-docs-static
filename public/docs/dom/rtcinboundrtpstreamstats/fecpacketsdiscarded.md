# RTCInboundRtpStreamStats.fecPacketsDiscarded

The `fecPacketsDiscarded` property of the [`RTCInboundRtpStreamStats`](../rtcinboundrtpstreamstats) dictionary is a numeric value indicating the number of [RTP](https://developer.mozilla.org/en-US/docs/Glossary/RTP) Forward Error Correction (FEC) packets that have been discarded.

## Syntax

    var fecPacketsDiscarded = rtcInboundRtpStreamStats.fecPacketsDiscarded;

### Value

An unsigned integer value indicating how many FEC packets have been received whose error correction payload has been discarded.

This can happen if all the packets covered by the FEC packet have already been received or recovered using another FEC packet, or if the FEC packet arrived outside the recovery window and the lost RTP packets have already been skipped during playback as a result. The value of `fecPacketsReceived` includes these discarded packets.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcinboundrtpstreamstats-fecpacketsdiscarded">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCInboundRtpStreamStats.fecPacketsDiscarded' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.RTCInboundRtpStreamStats.fecPacketsDiscarded`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCInboundRtpStreamStats/fecPacketsDiscarded" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCInboundRtpStreamStats/fecPacketsDiscarded</a>
