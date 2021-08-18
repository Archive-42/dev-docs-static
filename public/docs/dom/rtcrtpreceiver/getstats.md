RTCRtpReceiver.getStats()
=========================

The [`RTCRtpReceiver`](../rtcrtpreceiver) method `getStats()` asynchronously requests an [`RTCStatsReport`](../rtcstatsreport) object which provides statistics about incoming traffic on the owning [`RTCPeerConnection`](../rtcpeerconnection), returning a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) whose fulfillment handler will be called once the results are available.

Syntax
------

    var promise = RTCRtpReceiver.getStats();

### Return value

A JavaScript [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which is fulfilled once the statistics are available. The promise's fulfillment handler receives as a parameter a [`RTCStatsReport`](../rtcstatsreport) object containing the collected statistics.

The returned statistics include those from all streams which are coming in through the `RTCRtpReceiver`, as well as any of their dependencies.

Example
-------

This simple example obtains the statistics for an `RTCRtpReceiver` and updates an element's [`innerText`](../htmlelement/innertext) to display the number of packets lost.

    receiver.getStats().then(function(stats) {
      document.getElementById("lostpackets").innerText =
              stats.packetsLost;
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#widl-RTCRtpReceiver-getStats-Promise-RTCStatsReport">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCRtpReceiver.getStats()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`getStats`

67

≤18

55

No

54

12.1

67

67

55

48

12.2

7.0

See also
--------

-   [WebRTC API](../webrtc_api)
-   [`RTCStatsReport`](../rtcstatsreport)
-   [`RTCRtpSender.getStats()`](../rtcrtpsender/getstats)
-   [`RTCPeerConnection.getStats()`](../rtcpeerconnection/getstats)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpReceiver/getStats" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpReceiver/getStats</a>
