# RTCInboundRtpStreamStats.packetsDuplicated

The `packetsDuplicated` property of the [`RTCInboundRtpStreamStats`](../rtcinboundrtpstreamstats) dictionary indicates the total number of packets discarded because they were duplicates of previously-received packets. These packets are not counted by the <span class="page-not-created">`packetsDiscarded`</span> property.

## Syntax

    var packetsDuplicated = rtcInboundRtpStreamStats.packetsDuplicated;

### Value

An integer value which specifies how many duplcate packets have been received by the local end of this RTP stream so far. These duplicate packets are not included in the <span class="page-not-created">`packetsDiscarded`</span> property.

## Usage notes

Duplicate packets are detected when a packet has the same RTP sequence number as another packet that has previously been processed. Each time a packet is repeated, the value of `packetsDuplicated` is incremented, even if the same packet is received more than twice.

You can get a more accurate tally of how many packets have been lost on the stream by adding `packetsDuplicated` to <span class="page-not-created">`packetsLost`</span>. The resulting value will be positive, although it will not match the count as computed in [RFC 3660](https://tools.ietf.org/html/rfc3660).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcinboundrtpstreamstats-packetsduplicated">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCInboundRtpStreamStats.packetsDuplicated' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.RTCInboundRtpStreamStats.packetsDuplicated`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCInboundRtpStreamStats/packetsDuplicated" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCInboundRtpStreamStats/packetsDuplicated</a>
