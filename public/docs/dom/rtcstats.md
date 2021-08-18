RTCStats
========

The `RTCStats` dictionary is the basic statistics object used by WebRTC's statistics monitoring model, providing the properties required of all statistics data objects. Specific classes of statistic are defined as dictionaries based on `RTCStats`. For example, statistics about a received [RTP](https://developer.mozilla.org/en-US/docs/Glossary/RTP) stream are represented by <span class="page-not-created">`RTCReceivedRtpStreamStats`</span>.

Properties
----------

[`id`](rtcstats/id)  
A [`DOMString`](domstring) which uniquely identifies the object which was inspected to produce this object based on `RTCStats`.

[`timestamp`](rtcstats/timestamp)  
A [`DOMHighResTimeStamp`](domhighrestimestamp) object indicating the time at which the sample was taken for this statistics object.

[`type`](rtcstats/type)  
A [`DOMString`](domstring) indicating the type of statistics the object contains, taken from the enum type [`RTCStatsType`](rtcstatstype).

The statistics type hierarchy
-----------------------------

The various dictionaries that are used to define the contents of the objects that contain each of the various types of statistics for WebRTC are structured in such a way that they build upon the core `RTCStats` dictionary, each layer adding more relevant information.

-   [`RTCStats`](rtcstats) is the foundation of all WebRTC statistics objects
    -   [`RTCRtpStreamStats`](rtcrtpstreamstats) adds to `RTCStats` information that applies to all RTP endpoints (that is, both local and remote endpoints, and regardless of whether the endpoint is a sender or a receiver)
        -   <span class="page-not-created">`RTCReceivedRtpStreamStats`</span> further adds statistics measured at the receiving end of an RTP stream, regardless of whether it's local or remote.
            -   [`RTCInboundRtpStreamStats`](rtcinboundrtpstreamstats) contains statistics that can only be measured on a receiver at the local end of the RTP connection.
            -   [`RTCOutboundRtpStreamStats`](rtcoutboundrtpstreamstats) contains statistics related to the receiver at the remote end of the RTP stream.
        -   <span class="page-not-created">`RTCSentRtpStreamStats`</span> offers statistics related to the sending end of an RTP stream.
            -   [`RTCOutboundRtpStreamStats`](rtcoutboundrtpstreamstats) contains statistics about the local sending endpoint of an RTP stream.
            -   [`RTCRemoteOutboundRtpStreamStats`](rtcremoteoutboundrtpstreamstats) holds statistics related to the remote sending end an RTP stream.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcstats">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCStats' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.RTCStats`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCStats" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCStats</a>
