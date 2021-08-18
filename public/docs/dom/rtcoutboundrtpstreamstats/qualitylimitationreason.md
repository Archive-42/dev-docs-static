RTCOutboundRtpStreamStats.qualityLimitationReason
=================================================

The `qualityLimitationReason` property of the [`RTCOutboundRtpStreamStats`](../rtcoutboundrtpstreamstats) dictionary is a string indicating the reason why the media quality in the stream is currently being reduced by the codec during encoding, or `none` if no quality reduction is being performed. This quality reduction may include changes such as reduced frame rate or resolution, or an increase in compression factor.

The amount of time the encoded media has had its quality reduced in each of the potential ways that can be done can be found in <span class="page-not-created">`qualityLimitationDurations`</span>.

Syntax
------

    var qualityLimitationReason = RTCOutboundRtpStreamStats.qualityLimitationReason;

### Value

A [`Map`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map) whose keys are [`DOMString`](../domstring)s whose values come from the <span class="page-not-created">`RTCQualityLimitationReason`</span> enumerated type, and whose values are the duration of the media, in seconds, whose quality was reduced for that reason.

Examples
--------

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-RTCOutboundRtpStreamStats-qualityLimitationReason">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCOutboundRtpStreamStats.qualityLimitationReason' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.RTCOutboundRtpStreamStats.qualityLimitationReason`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCOutboundRtpStreamStats/qualityLimitationReason" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCOutboundRtpStreamStats/qualityLimitationReason</a>
