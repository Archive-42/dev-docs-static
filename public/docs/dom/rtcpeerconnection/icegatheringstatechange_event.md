RTCPeerConnection: icegatheringstatechange event
================================================

The `icegatheringstatechange` event is sent to the [`onicegatheringstatechange`](onicegatheringstatechange) event handler on an [`RTCPeerConnection`](../rtcpeerconnection) when the state of the [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) candidate gathering process changes. This signifies that the value of the connection's [`iceGatheringState`](icegatheringstate) property has changed.

When ICE firststarts to gather connection candidates, the value changes from `new` to `gathering` to indicate that the process of collecting candidate configurations for the connection has begun. When the value changes to `complete`, all of the transports that make up the `RTCPeerConnection` have finished gathering ICE candidates.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler</td><td><a href="onicegatheringstatechange"><code>onicegatheringstatechange</code></a></td></tr></tbody></table>

**Note:** While you can determine that ICE candidate gathering is complete by watching for `icegatheringstatechange` events and checking for the value of [`iceGatheringState`](icegatheringstate) to become `complete`, you can also have your handler for the [`icecandidate`](icecandidate_event) event look to see if its [`candidate`](../rtcpeerconnectioniceevent/candidate) property is `null`. This also indicates that collection of candidates is finished.

Examples
--------

This example creates a handler for `icegatheringstatechange` events.

    pc.onicegatheringstatechange = ev => {
      let connection = ev.target;

      switch(connection.iceGatheringState) {
        case "gathering":
          /* collection of candidates has begun */
          break;
        case "complete":
          /* collection of candidates is finished */
          break;
      }
    }

Likewise, you can use [`addEventListener()`](../eventtarget/addeventlistener) to add a listener for `icegatheringstatechange` events:

    pc.addEventListener("icegatheringstatechange", ev => {
      let connection = ev.target;

      switch(connection.iceGatheringState) {
        case "gathering":
          /* collection of candidates has begun */
          break;
        case "complete":
          /* collection of candidates is finished */
          break;
      }
    }, false);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#event-icegatheringstatechange">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'icecandidatestatechange' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.RTCPeerConnection.icegatheringstatechange_event`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

-   [WebRTC API](../webrtc_api)
-   [Signaling and video calling](../webrtc_api/signaling_and_video_calling)
-   [WebRTC connectivity](../webrtc_api/connectivity)
-   [Lifetime of a WebRTC session](../webrtc_api/session_lifetime)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/icegatheringstatechange_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/icegatheringstatechange_event</a>
