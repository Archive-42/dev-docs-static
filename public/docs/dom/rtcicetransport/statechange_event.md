RTCIceTransport: statechange event
==================================

A `statechange` event occurs when the [`RTCIceTransport`](../rtcicetransport) changes state. The [`state`](state) can be used to determine how far through the process of examining, verifying, and selecting a valid candidate pair is prior to successfully connecting the two peers for WebRTC communications.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onstatechange"><code>RTCIceTransport.onstatechange</code></a></td></tr></tbody></table>

Examples
--------

Given an [`RTCPeerConnection`](../rtcpeerconnection), `pc`, the following code creates an event handler that calls a function named `handleFailure()` if the ICE transport enters a failure state.

    let iceTransport = pc.getSenders()[0].transport.iceTransport;

    iceTransport.addEventListener("statechange", ev => {
      if (iceTransport.state === "failed") {
        handleFailure(pc);
      }
    }, false);

The same code, using the [`onstatechange`](onstatechange) event handler property, looks like this:

    let iceTransport = pc.getSenders()[0].transport.iceTransport;

    iceTransport.onstatechange = ev => {
      if (iceTransport.state === "failed") {
        handleFailure(pc);
      }
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#event-icetransport-statechange">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'statechange' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`statechange_event`

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
-   [`RTCIceTransport.onstatechange`](onstatechange) event handler

### Related RTCIceTransport events

-   `gatheringstatechange`
-   `selectedcandidatepairchange`

### Related RTCPeerConnection events

-   `negotiationneeded`
-   `signalingstatechange`
-   `iceconnectionstatechange`
-   `icegatheringstatechange`
-   `connectionstatechange`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/statechange_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/statechange_event</a>
