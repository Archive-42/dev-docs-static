RTCPeerConnection: negotiationneeded event
==========================================

A `negotiationneeded` event is sent to the [`RTCPeerConnection`](../rtcpeerconnection) when negotiation of the connection through the signaling channel is required. This occurs both during the initial setup of the connection as well as any time a change to the communication environment requires reconfiguring the connection.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onnegotiationneeded"><code>RTCPeerConnection.onnegotiationneeded</code></a></td></tr></tbody></table>

The `negotiationneeded` event is first dispatched to the [`RTCPeerConnection`](../rtcpeerconnection) when media is first added to the connection. This starts the process of [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) negotiation by instructing your code to begin exchanging ICE candidates through the signaling server. See [Signaling transaction flow](../webrtc_api/signaling_and_video_calling#signaling_transaction_flow) in [Signaling and video calling](../webrtc_api/signaling_and_video_calling) for a description of the signaling process that begins with a `negotiationneeded` event.

Examples
--------

In this example, we use [`addEventListener()`](../eventtarget/addeventlistener) to create an event handler for `negotiationneeded`. Its role is to create an [SDP](https://developer.mozilla.org/en-US/docs/Glossary/SDP) offer and send it through the signaling channel to the remote peer.

    pc.addEventListener("negotiationneeded", ev => {
      pc.createOffer()
      .then(offer => return pc.setLocalDescription(offer))
      .then(() => sendSignalingMessage({
        type: "video-offer",
        sdp: pc.localDescription
      }))
      .catch(err => {
        /* handle error */
      });
    }, false);

After creating the offer, the local end is configured by calling [`RTCPeerConnection.setLocalDescription()`](setlocaldescription); then a signaling message is created and sent to the remote peer through the signaling server, to share that offer with the other peer. The other peer should recognize this message and follow up by creating its own [`RTCPeerConnection`](../rtcpeerconnection), setting the remote description with [`setRemoteDescription()`](setremotedescription), and then creating an answer to send back to the offering peer.

You can also set an event handler for the `negotiationneeded` event by assigning the event handler function to the [`RTCPeerConnection.onnegotiationneeded`](onnegotiationneeded) property:

    pc.onnegotiationneeded = ev => {
      pc.createOffer()
      .then(offer => return pc.setLocalDescription(offer))
      .then(() => sendSignalingMessage({
        type: "video-offer",
        sdp: pc.localDescription
      }))
      .catch(err => {
        /* handle error */
      );
    };

For a more detailed example, see [Starting negotiation](../webrtc_api/signaling_and_video_calling#starting_negotiation) in [Signaling and video calling](../webrtc_api/signaling_and_video_calling).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#event-negotiation">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'negotiationneeded' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`negotiationneeded_event`

24

15

22

No

43

11

Yes

Yes

44

43

?

6.0

See also
--------

-   [WebRTC API](../webrtc_api)
-   [Signaling and video calling](../webrtc_api/signaling_and_video_calling)
-   [Lifetime of a WebRTC session](../webrtc_api/session_lifetime)
-   [WebRTC connectivity](../webrtc_api/connectivity)
-   [Introduction to WebRTC protocols](../webrtc_api/protocols)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/negotiationneeded_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/negotiationneeded_event</a>
