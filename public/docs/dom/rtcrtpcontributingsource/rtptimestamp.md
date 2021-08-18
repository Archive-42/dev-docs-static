RTCRtpContributingSource.rtpTimestamp
=====================================

The read-only `rtpTimestamp` property of the [`RTCRtpContributingSource`](../rtcrtpcontributingsource) interface returns a [`DOMHighResTimeStamp`](../domhighrestimestamp) indicating the source-generated time at which the media contained int he packet was first sampled or obtained.

Syntax
------

    let rtpTimestamp = RTCRtpContributingSource.rtpTimestamp

### Value

An integer value specifiying a source-generated timestamp indicating the time at which the media in this packet, scheduled for play out at the time indicated by [`timestamp`](timestamp), was initially sampled or generated. This value may be useful for sequencing and synchronization purposes.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcrtpsynchronizationsource-rtptimestamp">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'rtpTimestamp' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.RTCRtpContributingSource.rtpTimestamp`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpContributingSource/rtpTimestamp" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpContributingSource/rtpTimestamp</a>
