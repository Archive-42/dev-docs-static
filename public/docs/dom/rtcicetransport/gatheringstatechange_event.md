RTCIceTransport: gatheringstatechange event
===========================================

A `gatheringstatechange` event is sent to an [`RTCIceTransport`](../rtcicetransport) when its [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) candidate gathering state changes. The gathering state, whose actual status can be found in the transport object's [`gatheringState`](gatheringstate) property, indicates whether or not the ICE agent has begun gathering candidates, and if so, if it has finished doing so.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="ongatheringstatechange"><code>ongatheringstatechange</code></a></td></tr></tbody></table>

The key difference between `gatheringstatechange` and [`icegatheringstatechange`](../rtcpeerconnection/icegatheringstatechange_event) is that the latter represents the overall state of the connection including every [`RTCIceTransport`](../rtcicetransport) used by every [`RTCRtpSender`](../rtcrtpsender) and every [`RTCRtpReceiver`](../rtcrtpreceiver) on the entire connection. In contrast, `gatheringstatechange` represents changes to the candidate gathering state for a single transport.

Examples
--------

This example creates a handler for `gatheringstatechange` events on each [`RTCRtpSender`](../rtcrtpsender) associated with a given [`RTCPeerConnection`](../rtcpeerconnection). Here, the [`addEventListener()`](../eventtarget/addeventlistener) method is called to add a listener for `gatheringstatechange` events:

    pc.getSenders().forEach(sender => {
      sender.transport.iceTransport.addEventListener("gatheringstatechange", ev => {
      let transport = ev.target;

      if (transport.gatheringState === "complete") {
        /* this transport has finished gathering candidates,
           but others may still be working on it */
      }
    }, false);

Likewise, you can use the [`ongatheringstatechange`](ongatheringstatechange) event handler property:

    pc.getSenders().forEach(sender => {
      sender.transport.iceTransport.ongatheringstatechange = ev => {
        let transport = ev.target;

        if (transport.gatheringState === "complete") {
          /* this transport has finished gathering candidates,
             but others may still be working on it */
        }
      };
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#event-icetransport-gatheringstatechange">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'gatheringstatechange' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`gatheringstatechange_event`

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

-   [WebRTC API](../webrtc_api)
-   [WebRTC connectivity](../webrtc_api/connectivity)
-   [`RTCIceTransport.ongatheringstatechange`](ongatheringstatechange)

### Related RTCIceTransport events

-   `statechange`
-   `selectedcandidatepairchange`

### Related RTCPeerConnection events

-   `negotiationneeded`
-   `signalingstatechange`
-   `iceconnectionstatechange`
-   `icegatheringstatechange`
-   `connectionstatechange`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/gatheringstatechange_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/gatheringstatechange_event</a>
