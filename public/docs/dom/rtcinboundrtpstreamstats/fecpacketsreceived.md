RTCInboundRtpStreamStats.fecPacketsReceived
===========================================

The `fecPacketsReceived` property of the [`RTCInboundRtpStreamStats`](../rtcinboundrtpstreamstats) dictionary indicates how many Forward Error Correction (FEC) packets have been received by this RTP receiver from the remote peer. An FEC packet provides parity information which can be used to attempt to reconstruct RTP data packets which have been corrupted in transit.

Syntax
------

    var fecPacketsReceived = rtcInboundRtpStreamStats.fecPacketsReceived;

### Value

An unsigned integer value which indicates the total number of FEC packets which have been received from the remote peer during this RTP session. Forward Error Correction uses an exclusive-or method to perform parity checks on the received data.

By using the FEC parity information to attempt to reconstruct damaged packets, it is possible to avoid the need to retransmit damaged packets, which in turn helps to reduce lag, or the need to skip damaged frames entirely.

**Note:** This counter may also be incremented when FEC packets arrive in-band along with media content; this can happen with Opus, for example.

Usage notes
-----------

It's possible that a subset of the FEC packets which have been received were discarded instead of being used. This can happen if the packets covered by the FEC packets have already been received successfully or have already been reconstructed using a previously-received FEC packet. This may also happen if the FEC packet arrives outside the window of time in which the client will attempt to use it.

If you wish to know how many of the received packets were discarded, you can examine the value of [`fecPacketsDiscarded`](fecpacketsdiscarded).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcinboundrtpstreamstats-fecpacketsreceived">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCInboundRtpStreamStats.fecPacketsReceived' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.RTCInboundRtpStreamStats.fecPacketsReceived`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

-   [RFC 5109](https://tools.ietf.org/html/rfc5109) (RTP Payload Format for Generic Forward Error Correction)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCInboundRtpStreamStats/fecPacketsReceived" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCInboundRtpStreamStats/fecPacketsReceived</a>
