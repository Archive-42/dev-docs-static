RTCRtpSender.getStats()
=======================

The [`RTCRtpSender`](../rtcrtpsender) method `getStats()` asynchronously requests an [`RTCStatsReport`](../rtcstatsreport) object which provides statistics about outgoing traffic on the [`RTCPeerConnection`](../rtcpeerconnection) which owns the sender, returning a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which is fulfilled when the results are available.

Syntax
------

    var promise = RTCRtpSender.getStats();

### Return value

A JavaScript [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which is fulfilled once the statistics are available. The promise's fulfillment handler receives as a parameter a [`RTCStatsReport`](../rtcstatsreport) object containing the collected statistics.

The returned `RTCStatsReport` accumulates the statistics for all of the streams being sent using the `RTCRtpSender`, as well as the statistics for any dependencies those streams have.

Example
-------

This simple example obtains the statistics for an `RTCRtpSender` and updates an element's [`innerText`](../htmlelement/innertext) to display the current round trip time for requests on the sender.

    sender.getStats().then(function(stats) {
      document.getElementById("currentRTT").innerText =
              stats.roundTripTime;
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#widl-RTCRtpSender-getStats-Promise-RTCStatsReport">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCRtpSender.getStats()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

9.0

See also
--------

-   [WebRTC](https://developer.mozilla.org/en-US/docs/Web/Guide/API/WebRTC_API)
-   [`RTCStatsReport`](../rtcstatsreport)
-   [`RTCRtpReceiver.getStats()`](../rtcrtpreceiver/getstats)
-   [`RTCPeerConnection.getStats()`](../rtcpeerconnection/getstats)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSender/getStats" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSender/getStats</a>
