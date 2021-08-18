RTCIceCandidateStats.deleted
============================

  
The [`RTCIceCandidateStats`](../rtcicecandidatestats) dictionary's `deleted` property indicates whether or not the candidate has been deleted or released.

Syntax
------

    isDeleted = rtcIceCandidateStats.deleted;

### Value

A Boolean value indicating whether or not the candidate has been deleted or released. If this value is `true`, the candidate described by the [`RTCIceCandidateStats`](../rtcicecandidatestats) object is no longer under consideration. dThe exact meaning varies depending on the type of candidate:

Local candidate  
A value of `true` means the candidate has been deleted as described by [RFC 5245: 8.3](https://tools.ietf.org/html/rfc5245).

Host candidate  
A value of `true` indicates that the candidate's network resources have been released. This generally mean sthat any associated socket(s) have been closed and released.

Remote (TURN) candidate  
A value of `true` means the candidate's [TURN](https://developer.mozilla.org/en-US/docs/Glossary/TURN) allocation is no longer active.

The net result is the same; the candidate is no longer under consideration if this value is `true`.

Example
-------

In this example, [`setInterval()`](../windoworworkerglobalscope/setinterval) is used to set up a function that runs periodically to display the latest statistics for candidates. Only candidates which have not been deleted are included in the output.

    window.setInterval(function() {
      myPeerConnection.getStats(null).then(stats => {
        let statsOutput = "";

        stats.forEach(report => {
          if ((stats.type === "local-candidate" || stats.type === "remote.candidate") && !stats.deleted) {
            statsOutput += `<h2>Report: ${report.type}</h3>\n<strong>ID:</strong> ${report.id}<br>\n` +
                           `<strong>Timestamp:</strong> ${report.timestamp}<br>\n`;

            // Now the statistics for this report; we intentially drop the ones we
            // sorted to the top above

            Object.keys(report).forEach(statName => {
              if (statName !== "id" && statName !== "timestamp" && statName !== "type") {
                statsOutput += `<strong>${statName}:</strong> ${report[statName]}<br>\n`;
              }
            });
          }
        });

        document.querySelector(".stats-box").innerHTML = statsOutput;
      });
    }, 1000);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcicecandidatestats-deleted">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCIceCandidateStats.deleted' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`deleted`

No

No

No

No

?

?

No

No

No

?

?

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidateStats/deleted" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidateStats/deleted</a>
