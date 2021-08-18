RTCInboundRtpStreamStats.averageRtcpInterval
============================================

The `averageRtcpInterval` property of the [`RTCInboundRtpStreamStats`](../rtcinboundrtpstreamstats) dictionary is a floating-point value indicating the average [RTCP](https://developer.mozilla.org/en-US/docs/Glossary/RTCP) transmission interval, in seconds. The RTCP interval is the amount of time that should elapse between transmissions of RTCP packets.

Syntax
------

    var averageRtcpInterval = rtcInboundRtpStreamStats.averageRtcpInterval;

### Value

A floating-point value indicating the average interval, in seconds, between transmissions of RTCP packets. This interval is computed following the formula outlined in [RFC 1889: A.7](https://tools.ietf.org/html/rfc1889).

Because the interval's value is determined in part by the number of active senders, it will be different for each user of a service. Since this value is also used to determine the number of seconds after a stream starts to flow before the first RTCP packet should be sent, the result is that if many users try to start using the service at the same time, the server won't be flooded with RTCP packets coming in all at once.

The sending endpoint computes this value when sending compound RTCP packets, which must contain at least an RTCP RR or SR packet and an SDES packet with the CNAME item.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcinboundrtpstreamstats-averagertcpinterval">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCInboundRtpStreamStats.averageRtcpInterval' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.RTCInboundRtpStreamStats.averageRtcpInterval`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCInboundRtpStreamStats/averageRtcpInterval" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCInboundRtpStreamStats/averageRtcpInterval</a>
