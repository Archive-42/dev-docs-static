RTCPeerConnection: connectionstatechange event
==============================================

The `connectionstatechange` event is sent to the [`ontrack`](ontrack) event handler on an [`RTCPeerConnection`](../rtcpeerconnection) object after a new track has been added to an [`RTCRtpReceiver`](../rtcrtpreceiver) which is part of the connection. The new connection state can be found in [`connectionState`](connectionstate), and is one of the strings in the <span class="page-not-created">`RTCPeerConnectionState`</span> enumerated type.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler</td><td><a href="onconnectionstatechange"><code>onconnectionstatechange</code></a></td></tr></tbody></table>

Examples
--------

For an [`RTCPeerConnection`](../rtcpeerconnection), `pc`, this example sets up a handler for `connectionstatechange` messages to handle changes to the connectivity of the WebRTC session. It calls an app-defined function called `setOnlineStatus()` to update a status display.

    pc.onconnectionstatechange = ev => {
      switch(pc.connectionState) {
        case "new":
        case "checking":
          setOnlineStatus("Connecting...");
          break;
        case "connected":
          setOnlineStatus("Online");
          break;
        case "disconnected":
          setOnlineStatus("Disconnecting...");
          break;
        case "closed":
          setOnlineStatus("Offline");
          break;
        case "failed":
          setOnlineStatus("Error");
          break;
        default:
          setOnlineStatus("Unknown");
          break;
      }
    }

You can also create a handler for `connectionstatechange` by using [`addEventListener()`](../eventtarget/addeventlistener):

    pc.addEventListener("connectionstatechange", ev => {
      switch(pc.connectionState) {
        /* ... */
      }
    }, false);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#event-connectionstatechange">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'connectionstatechange' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`connectionstatechange_event`

72

79

No

No

No

11

72

72

No

No

No

11.0

See also
--------

-   [WebRTC API](../webrtc_api)
-   [WebRTC connectivity](../webrtc_api/connectivity)
-   [Lifetime of a WebRTC session](../webrtc_api/session_lifetime)
-   <span class="page-not-created">`RTCPeerConnectionState`</span>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/connectionstatechange_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/connectionstatechange_event</a>
