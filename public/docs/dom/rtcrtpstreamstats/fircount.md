RTCRtpStreamStats.firCount
==========================

The `firCount` property of the [`RTCRtpStreamStats`](../rtcrtpstreamstats) dictionary indicates the number of **Full Intra Request** (**FIR**) packets have been sent by the receiver to the sender. This is a measure of how often the stream falls behind and has to skip frames in order to catch up.

Syntax
------

    var firCount = RTCRtpStreamStats.firCount;

### Value

An integer value indicating how many FIR packets have been received by the sender during the current connection. This value is available only on receivers for video tracks.

The receiver sends a FIR packet to the sender any time it falls bahind or loses packets and cannot decode the incoming stream any longer because of the lost data. This tells the sender to send a full frame instead of a delta frame, so that the receiver can catch up.

The higher `firCount` is, the more often frames were dropped, which may be an indication that the media's bit rate is too high for the available bandwidth, or that the receiving device is overburdened and is therefore unable to process the incoming data.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcinboundrtpstreamstats-fircount">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCInboundRtpStreamStats: firCount' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcoutboundrtpstreamstats-fircount">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCOutboundRtpStreamStats: firCount' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`firCount`

No

No

55

No

No

?

No

No

55

No

?

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpStreamStats/firCount" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpStreamStats/firCount</a>
