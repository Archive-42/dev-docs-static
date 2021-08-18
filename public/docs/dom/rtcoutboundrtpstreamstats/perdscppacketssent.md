RTCOutboundRtpStreamStats.perDscpPacketsSent
============================================

The `perDscpPacketsSent` property of the [`RTCOutboundRtpStreamStats`](../rtcoutboundrtpstreamstats) dictionary is a record comprised of key/value pairs in which each key is a string representation of a Differentiated Services Code Point and the value is the number of packets sent for that DCSP.

**Note:** Not all operating systems make data available on a per-DSCP basis, so this property shouldn't be relied upon on those systems.

Syntax
------

    var perDscpPacketsSent = RTCOutboundRtpStreamStats.perDscpPacketsSent;

### Value

A record comprised of string/value pairs. Each key is the string representation of a single Differentiated Services Code Point (DSCP)'s ID number.

**Note:** Due to network bleaching and remapping, the numbers seen on this record are not necessarily going to match the values as they were when the data was sent.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-RTCOutboundRtpStreamStats-perDscpPacketsSent">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCOutboundRtpStreamStats.perDscpPacketsSent' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.RTCOutboundRtpStreamStats.perDscpPacketsSent`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

-   [RFC 2474](https://tools.ietf.org/html/rfc2474): The Differentiated Service field in IPv4 and IPv6 headers

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCOutboundRtpStreamStats/perDscpPacketsSent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCOutboundRtpStreamStats/perDscpPacketsSent</a>
