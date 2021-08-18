# RTCInboundRtpStreamStats.packetsFailedDecryption

The `packetsFailedDecryption` property of the [`RTCInboundRtpStreamStats`](../rtcinboundrtpstreamstats) dictionary indicates the total number of [RTP](https://developer.mozilla.org/en-US/docs/Glossary/RTP) packets which failed to be decrypted successfully after being received by the local end of the connection during this session.

## Syntax

    var packetsFailedDecryption = rtcInboundRtpStreamStats.packetsFailedDecryption;

### Value

An integer value which indicates how many packets the local end of the RTP connection could not be successfully decrypted.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcinboundrtpstreamstats-packetsfaileddecryption">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCInboundRtpStreamStats.packetsFailedDecryption' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.RTCInboundRtpStreamStats.packetsFailedDecryption`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

## See also

- [RFC 3711: 3.3](https://tools.ietf.org/html/rfc3711): Description of the decryption process for secure RTP packets

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCInboundRtpStreamStats/packetsFailedDecryption" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCInboundRtpStreamStats/packetsFailedDecryption</a>
