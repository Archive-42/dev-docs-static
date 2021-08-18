RTCStats.type
=============

The [`RTCStats`](../rtcstats) dictionary's property `type` is a string which specifies the type of statistic represented by the object, where the permitted values are drawn from the enum type [`RTCStatsType`](../rtcstatstype). The string can be used to determine which of the [`RTCStats`](../rtcstats)-based dictionaries are the foundation of the statistics object.

Syntax
------

    var type = RTCStats.type;

### Value

A [`DOMString`](../domstring) which specifies which type of statistic is represented by the object. The string comes from the [`RTCStatsType`](../rtcstatstype) enum and corrsponds to one of the [`RTCStats`](../rtcstats)-based statistic object types.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcstats-type">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCStats.type' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.RTCStats.type`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCStats/type" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCStats/type</a>
