RTCIceTransport: selectedcandidatepairchange event
==================================================

A `selectedcandidatepairchange` event is sent to an [`RTCIceTransport`](../rtcicetransport) when the [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) agent selects a new pair of candidates that describe the endpoints of a viable connection. The pair of candidates is in turn described by an [`RTCIceCandidatePair`](../rtcicecandidatepair) object which contains one [`RTCIceCandidate`](../rtcicecandidate) representing the local end of the connection, and another representing the remote end of the connection.

Together, the candidates can be used to establish a connection to be used by the [`RTCIceTransport`](../rtcicetransport), and, by extension, by an [`RTCPeerConnection`](../rtcpeerconnection).

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onselectedcandidatepairchange"><code>onselectedcandidatepairchange</code></a></td></tr></tbody></table>

Examples
--------

This example creates an event handler for `selectedcandidatepairchange` that updates a display providing the user information about the progress of the ICE negotiation for an [`RTCPeerConnection`](../rtcpeerconnection) called `pc`.

    let iceTransport = pc.getSenders[0].transport.iceTransport;
    let localProtoElem = document.getElementById("local-protocol");
    let remoteProtoElem = document.getElementById("remote-protocol");

    iceTransport.addEventListener("selectedcandidatepairchange", ev => {
      let pair = iceTransport.getSelectedCandidatePair();
      localProtoElem.innerText = pair.local.protocol.toUpperCase();
      remoteProtoElem.innerText = pair.remote.protocol.toUpperCase();
    }, false)

This can also be done by setting the [`onselectedcandidatepairchange`](onselectedcandidatepairchange) event handler property directly.

    let iceTransport = pc.getSenders[0].transport.iceTransport;
    let localProtoElem = document.getElementById("local-protocol");
    let remoteProtoElem = document.getElementById("remote-protocol");

    iceTransport.onselectedcandidatepairchange = ev => {
      let pair = iceTransport.getSelectedCandidatePair();
      localProtoElem.innerText = pair.local.protocol.toUpperCase();
      remoteProtoElem.innerText = pair.remote.protocol.toUpperCase();
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#event-icetransport-selectedcandidatepairchange">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'selectedcandidatepairchange' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`selectedcandidatepairchange_event`

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
-   [`RTCIceTransport.onselectedcandidatepairchange`](onselectedcandidatepairchange)

### Related RTCIceTransport events

-   `statechange`
-   `gatheringstatechange`

### Related RTCPeerConnection events

-   `negotiationneeded`
-   `signalingstatechange`
-   `iceconnectionstatechange`
-   `icegatheringstatechange`
-   `connectionstatechange`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/selectedcandidatepairchange_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/selectedcandidatepairchange_event</a>
