RTCRtpContributingSource.timestamp
==================================

The read-only `timestamp` property of the [`RTCRtpContributingSource`](../rtcrtpcontributingsource) interface returns a [`DOMHighResTimeStamp`](../domhighrestimestamp) indicating the most recent time of playout of an RTP packet from the source.

Syntax
------

    var domHighResTimeStamp = RTCRtpContributingSource.timestamp

### Value

A [`DOMHighResTimeStamp`](../domhighrestimestamp) which indicates the time at which the most recent RTP packet from the corresponding source was played out.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcrtpcontributingsource-timestamp">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'timestamp' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`timestamp`

59

≤79

59

Starting in version 60, the `timestamp` is correctly computed based on the window's `Performance` time, rather than `Date.getTime()`.

No

No

?

59

59

59

Starting in version 60, the `timestamp` is correctly computed based on the window's `Performance` time, rather than `Date.getTime()`.

No

?

7.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpContributingSource/timestamp" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpContributingSource/timestamp</a>
