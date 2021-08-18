RTCPeerConnection.getStats()
============================

The [`RTCPeerConnection`](../rtcpeerconnection) method `getStats()` returns a promise which resolves with data providing statistics about either the overall connection or about the specified [`MediaStreamTrack`](../mediastreamtrack).

Syntax
------

    promise = rtcPeerConnection.getStats(selector)

### Parameters

 `selector` <span class="badge inline optional">Optional</span>   
A [`MediaStreamTrack`](../mediastreamtrack) for which to gather statistics. If this is `null` (the default value), statistics will be gathered for the entire [`RTCPeerConnection`](../rtcpeerconnection).

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which resolves with an [`RTCStatsReport`](../rtcstatsreport) object providing connection statistics. The contents of the report depend on the `selector` as well as other details of the connection.

### Exceptions

This method does not throw exceptions; instead, it rejects the returned promise with one of the following errors:

`InvalidAccessError`  
There is no [`RTCRtpSender`](../rtcrtpsender) or [`RTCRtpReceiver`](../rtcrtpreceiver) whose `track` matches the specified `selector`, or `selector` matches more than one sender or receiver.

### Obsolete syntax

Previously, `getStats()` used success and failure callbacks to report the results to you, instead of using a promise.

This version of `getStats()` is obsolete; in addition, the data it returns is entirely different from the current specification, and the form of that data was never documented. This form of `getStats()` has been or will soon be removed from most browsers; you *should not use it, and should update existing code to use the new promise-based version*. Check the [Browser compatibility](#browser_compatibility) table to verify the state of this method.

    promise = rtcPeerConnection.getStats(selector, successCallback, failureCallback) 
        This deprecated API should no longer be used, but will probably still work.
        

#### Parameters

 `selector` <span class="badge inline optional">Optional</span>   
A [`MediaStreamTrack`](../mediastreamtrack) for which to gather statistics. If this is `null` (the default value), statistics will be gathered for the entire [`RTCPeerConnection`](../rtcpeerconnection).

`successCallback`  
A callback function to call when the stats have been retrieved. The function receives as input a single parameter: an [`RTCStatsReport`](../rtcstatsreport) with the collected statistics. No output is expected from the function.

`failureCallback`  
A function to call when an error occurs while attempting to collect statistics. The callback receives as input the exception (a [`DOMException`](../domexception) object describing the error which occurred. No return value is expected from the callback.

Example
-------

This example creates a periodic function using [`setInterval()`](../windoworworkerglobalscope/setinterval) that collects statistics for an [`RTCPeerConnection`](../rtcpeerconnection) every second, generating an HTML-formatted report and inserting it into a specific element in the DOM.

    window.setInterval(function() {
      myPeerConnection.getStats(null).then(stats => {
        let statsOutput = "";

        stats.forEach(report => {
          statsOutput += `<h2>Report: ${report.type}</h2>\n<strong>ID:</strong> ${report.id}<br>\n` +
                         `<strong>Timestamp:</strong> ${report.timestamp}<br>\n`;

          // Now the statistics for this report; we intentially drop the ones we
          // sorted to the top above

          Object.keys(report).forEach(statName => {
            if (statName !== "id" && statName !== "timestamp" && statName !== "type") {
              statsOutput += `<strong>${statName}:</strong> ${report[statName]}<br>\n`;
            }
          });
        });

        document.querySelector(".stats-box").innerHTML = statsOutput;
      });
    }, 1000);

This works by calling `getStats()`, then, when the promise is resolved, iterates over the [`RTCStats`](../rtcstats) objects on the returned [`RTCStatsReport`](../rtcstatsreport). A section is created for each report with a header and all of the statistics below, with the type, ID, and timestamp handled specially to place them at the top of the list.

Once the [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML) for the report is generated, it is injected into the element whose class is `"stats-box"` by setting its [`innerHTML`](../element/innerhtml) property.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#widl-RTCPeerConnection-getStats-Promise-RTCStatsReport--MediaStreamTrack-selector">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCPeerConnection.getStats()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

58

Promise resolves with `RTCStatsReport`.

54

Promise-based version.

24

15

Yes

No

45

11

58

Promise resolves with `RTCStatsReport`.

54

Promise-based version.

Yes

58

Promise resolves with `RTCStatsReport`.

54

Promise-based version.

Yes

Yes

43

11

7.0

Promise resolves with `RTCStatsReport`.

6.0

Promise-based version.

Yes

`MediaStreamTrack_argument`

67

≤79

?

No

54

?

67

67

?

48

?

9.0

`with_callbacks`

24

15

27-66

No

45

11

Yes

Yes

?

43

?

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/getStats" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/getStats</a>
