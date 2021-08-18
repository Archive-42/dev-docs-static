RTCRemoteOutboundRtpStreamStats.reportsSent
===========================================

The [`RTCRemoteOutboundRtpStreamStats`](../rtcremoteoutboundrtpstreamstats) dictionary's `reportsSent` property provides the number of Sender Reports (SRs) the remote peer has transmitted to the local peer.

Syntax
------

    let reportCount = rtcRemoteOutboundRtpStreamStats.reportsSent;

### Value

An integer value which indicates the total number of RTCP Sender Reports so far sent by the remote peer to the local peer.

Usage notes
-----------

Sender reports, described in [RFC 3550, section 6.4.1](https://tools.ietf.org/html/rfc3550#section-6.4.1) with an overview in [RFC 3550, section 6.4](https://tools.ietf.org/html/rfc3550#section-6.4), are used by RTP to share data transmission quality feedback between the two peers. The data in these reports is used by WebRTC to fill out various fields within the statistics objects, and this property's value indicates how many times that information was shared.

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

`reportsSent`

No

No

No

No

No

No

No

No

No

No

No

No

See also
--------

-   [RFC 3550, section 6.4: RTP: A Transport Protocol for Real-Time Applications](https://tools.ietf.org/html/rfc3550#section-6.4)
-   The <span class="page-not-created">`RTCRemoteinboundRtpStreamStats`</span> property <span class="page-not-created">`reportsReceived`</span>; the number of RTCP Receiver Report (RR) records received from the remote peer

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRemoteOutboundRtpStreamStats/reportsSent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRemoteOutboundRtpStreamStats/reportsSent</a>
