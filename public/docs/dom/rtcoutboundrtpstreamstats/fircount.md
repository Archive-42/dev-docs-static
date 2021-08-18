RTCOutboundRtpStreamStats.firCount
==================================

The `firCount` property of the [`RTCOutboundRtpStreamStats`](../rtcoutboundrtpstreamstats) dictionary indicates the number of **Full Intra Request** (**FIR**) that the remote [`RTCRtpReceiver`](../rtcrtpreceiver) has sent to this [`RTCRtpSender`](../rtcrtpsender). A FIR packet is sent when the receiver finds that it has fallen behind and needs to skip frames in order to catch up; the sender should respond by sending a full frame instead of a delta frame.

Available only on video media.

Syntax
------

    var firCount = RTCOutboundRtpStreamStats.firCount;

### Value

An integer value indicating how many FIR packets have been received by the sender during the current connection. This statistic is available only for video tracks.

The receiver sends a FIR packet to the sender any time it falls bahind or loses packets and cannot decode the incoming stream any longer because of the lost data. This tells the sender to send a full frame instead of a delta frame, so that the receiver can catch up.

The higher `firCount` is, the more often frames were dropped, which may be an indication that the media's bit rate is too high for the available bandwidth, or that the receiving device is overburdened and is therefore unable to process the incoming data.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-RTCOutboundRtpStreamStats-fircount">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCOutboundRtpStreamStats.firCount' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.RTCOutboundRtpStreamStats.firCount`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCOutboundRtpStreamStats/firCount" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCOutboundRtpStreamStats/firCount</a>
