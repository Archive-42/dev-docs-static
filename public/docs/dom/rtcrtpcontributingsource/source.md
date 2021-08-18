RTCRtpContributingSource.source
===============================

The read-only `source` property of the [`RTCRtpContributingSource`](../rtcrtpcontributingsource) interface returns the source identifier of a particular stream of RTP packets. The value is the contributing source (CSRC) or synchronization source (SSRC) identifier, depending on whether the object is an `RTCRtpContributingSource` or [`RTCRtpSynchronizationSource`](../rtcrtpsynchronizationsource), which is based on the former.

Syntax
------

    var sourceID = RTCRtpContributingSource.source

### Value

An unsigned, 32-bit integer value which uniquely identifies the source of RTP packets described by this `RTCRtpContributingSource` (in which case the value is a CSRC identifier) or `RTCRtpSynchronizationSource` (the value is an SSRC identifier).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcrtpcontributingsource-source">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'source' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

Desktop

Mobile

Chrome

Edge

Firefox

Internet Explorer

Opera

Safari

WebView Android

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

`source`

59

≤79

59

No

No

?

59

59

59

No

?

7.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpContributingSource/source" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpContributingSource/source</a>
