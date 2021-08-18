RTCStats.id
===========

The `id` property of the [`RTCStats`](../rtcstats) dictionary is a string which uniquely identifies the object for which this `RTCStats` object provides statistics. Using the `id`, you can correlate two or more `RTCStats`-based objects in order to monitor statistics over time for a given WebRTC object, such as an [RTP](https://developer.mozilla.org/en-US/docs/Glossary/RTP) stream, an [`RTCPeerConnection`](../rtcpeerconnection), or an [`RTCDataChannel`](../rtcdatachannel).

Syntax
------

    var id = RTCStats.id;

### Value

A [`DOMString`](../domstring) which uniquely identifies the object for which this `RTCStats`-based object provides statistics.

The format of the ID string is not defined by the specification, so you cannot reliably make any assumptions about the contents of the string, or assume that the format of the string will remain unchanged for a given object type.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcstats-id">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCStats.id' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.RTCStats.id`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCStats/id" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCStats/id</a>
