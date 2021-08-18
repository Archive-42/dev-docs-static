RTCRemoteOutboundRtpStreamStats.remoteTimestamp
===============================================

The [`RTCRemoteOutboundRtpStreamStats`](../rtcremoteoutboundrtpstreamstats) property `remoteTimestamp` indicates the timestamp on the remote peer at which these statistics were sent. This differs from `timestamp`, which indicates the time at which the statistics were generated or received locally.

Syntax
------

    let remoteTimestamp = rtcRemoteOutboundRtpStreamStats.remoteTimestamp;

### Value

A [`DOMHighResTimeStamp`](../domhighrestimestamp) value indicating the timestamp on the remote peer at which it sent these statistics. This is different from the value `timestamp`, which gives the time at which the statistics were generated or received by the local peer.

If this property is present, it comes from the [RTCP](https://developer.mozilla.org/en-US/docs/Glossary/RTCP) Sender Report (SR) block, which reflects the clock on the remote peer at the time the message was sent. Keep in mind that this means the clock may not be synchronized with the local clock, and that both the current time and the pace at which the clock runs may differ to some extent.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcremoteoutboundrtpstreamstats-remotetimestamp">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCRemoteOutboundRtpStreamStats.remoteTimestamp' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`remoteTimestamp`

No

No

79

No

No

No

No

No

79

No

No

No

See also
--------

-   [`RTCStats.timestamp`](../rtcstats/timestamp)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRemoteOutboundRtpStreamStats/remoteTimestamp" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRemoteOutboundRtpStreamStats/remoteTimestamp</a>
