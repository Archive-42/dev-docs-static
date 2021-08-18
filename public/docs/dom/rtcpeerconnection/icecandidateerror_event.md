RTCPeerConnection: icecandidateerror event
==========================================

The [WebRTC API](../webrtc_api) event `icecandidateerror` is sent to an [`RTCPeerConnection`](../rtcpeerconnection) if an error occurs while performing ICE negotiations through a [STUN](https://developer.mozilla.org/en-US/docs/Glossary/STUN) or [TURN](https://developer.mozilla.org/en-US/docs/Glossary/TURN) server. The event object is of type [`RTCPeerConnectionIceErrorEvent`](../rtcpeerconnectioniceerrorevent), and contains information describing the error in some amount of detail.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../rtcpeerconnectioniceerrorevent"><code>RTCPeerConnectionIceErrorEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onicecandidateerror"><code>RTCPeerConnection.onicecandidateerror</code></a></td></tr></tbody></table>

Description
-----------

The error object's <span class="page-not-created">`errorCode`</span> property is one of the numeric STUN error codes. There is one additional, WebRTC-specific, error which lies outside the valid STUN error code range: 701. Error 701 indicates that none of the ICE candidates were able to successfully make contact with the STUN or TURN server.

The 701 error is fired only once per server URL from the list of available STUN or TURN servers provided when creating the [`RTCPeerConnection`](../rtcpeerconnection). These errors occur only when the connection's [ICE gathering state](icegatheringstate) is `gathering`.

Example
-------

The following example establishes a handler for `icecandidateerror`s that occur on the [`RTCPeerConnection`](../rtcpeerconnection) `pc`. This handler looks specifically for 701 errors that indicate that candidates couldn't reach the STUN or TURN server.

When this happens, the server URL and the error message are passed to a function called `reportConnectFail()` to log or output the connection failure.

    pc.addEventListener("icecandidateerror", (event) => {
      if (event.errorCode === 701) {
        reportConnectFail(event.url, event.errorText);
      }
    });

Note that if multiple STUN and/or TURN servers are provided when creating the connection, this error may happen more than once, if more than one of those servers fails. Each provided server is tried until a connection is established.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#event-icecandidateerror">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'icecandidateerror' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.RTCPeerConnection.icecandidateerror_event`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/icecandidateerror_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/icecandidateerror_event</a>
