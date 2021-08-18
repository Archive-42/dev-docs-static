RTCRtpStreamStats.trackId
=========================

The [`RTCRtpStreamStats`](../rtcrtpstreamstats) dictionary's `trackId` property is a string which uniquely identifies the <span class="page-not-created">`RTCMediaStreamTrackStats`</span> object which contains the track statistics for the [`MediaStreamTrack`](../mediastreamtrack) for which statistics are provided in this object.

Syntax
------

    var trackID = RTCRtpStreamStats.trackId;

### Value

A [`DOMString`](../domstring) which uniquely identifies the <span class="page-not-created">`RTCMediaStreamTrackStats`</span> object that provides statistics for the track for which statistics are being collected by this [`RTCStatsReport`](../rtcstatsreport).

**Note:** This value is *not* the same as the value of <span class="page-not-created">`MediaStramTrack.id`</span>.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcrtpstreamstats-trackid">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCRtpStreamStats.trackId' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.RTCRtpStreamStats.trackId`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpStreamStats/trackId" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpStreamStats/trackId</a>
