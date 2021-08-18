# RTCInboundRtpStreamStats.bytesReceived

The [`RTCInboundRtpStreamStats`](../rtcinboundrtpstreamstats) dictionary's `bytesReceived` property is an integer value which indicates the total number of bytes received so far from this synchronization source (SSRC).

## Syntax

    var bytesReceived = rtcInboundRtpStreamStats.bytesReceived;

### Value

An unsigned integer value indicating the total number of bytes received so far on this RTP stream, not including header and padding bytes. This value can be used to calculate an approximation of the average media data rate:

    avgDataRate = rtcInboundRtpStreamStats.bytesReceived / elapsedTime;

This value gets reset to zero if the sender's SSRC identifier changes for any reason.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcinboundrtpstreamstats-bytesreceived">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCInboundRtpStreamStats.bytesReceived' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.RTCInboundRtpStreamStats.bytesReceived`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCInboundRtpStreamStats/bytesReceived" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCInboundRtpStreamStats/bytesReceived</a>
