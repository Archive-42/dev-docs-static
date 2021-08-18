RTCStats.timestamp
==================

The `timestamp` property of the [`RTCStats`](../rtcstats) dictionary is a [`DOMHighResTimeStamp`](../domhighrestimestamp) object specifying the time at which the data in the object was sampled. For reports related to RTCP packets, for instance, this indicates the time at which the data covered by the statistics was received at the corresponding endpoint.

The time is given in milliseconds elapsed since the UNIX epoch (the first moment of January 1, 1970, UTC).

Syntax
------

    var timestamp = RTCStats.timestamp;

### Value

A [`DOMHighResTimeStamp`](../domhighrestimestamp) value indicating the time at which the activity described by the statistics in this object was recorded, in milliseconds elapsed since the beginning of January 1, 1970, UTC. This should be accurate to within a few milliseconds but may not be entirely pricise, either because of hardware or operating system limitations or because of fingerprinting protection in the form of reduced clock precision or accuracy.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcstats-timestamp">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCStats.timestamp' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.RTCStats.timestamp`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCStats/timestamp" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCStats/timestamp</a>
