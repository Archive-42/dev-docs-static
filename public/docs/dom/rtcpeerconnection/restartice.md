RTCPeerConnection.restartIce()
==============================

The [WebRTC](../webrtc_api) API's [`RTCPeerConnection`](../rtcpeerconnection) interface offers the `restartIce()` method to allow a web application to easily request that [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) candidate gathering be redone on both ends of the connection. This simplifies the process by allowing the same method to be used by either the caller or the receiver to trigger an ICE restart.

After `restartIce()` returns, the offer returned by the next call to [`createOffer()`](createoffer) is automatically configured to trigger ICE restart on both the local peer (once the local peer has been set) and on the remote peer, once the offer is sent across your signaling mechanism and the remote peer has set its description as well.

`restartIce()` causes the [`negotiationneeded`](negotiationneeded_event) event to be fired on the `RTCPeerConnection` to inform the application that it should perform negotiation using its signaling channel.

If negotiation fails to complete—either due to rollback or because incoming offers are in the process of being negotiated—the [`RTCPeerConnection`](../rtcpeerconnection) will remember that you requested ICE restart. The next time the connection's [`signalingState`](signalingstate) changes to `stable`, the connection will fire the [`negotiationneeded`](negotiationneeded_event) event. This process continues until an ICE restart has been successfully completed.

Syntax
------

    rtcPeerConnection.restartIce();

### Parameters

None.

### Return value

`undefined`.

Usage notes
-----------

After calling `restartIce()`, the next offer created using [`createOffer()`](createoffer) will initiate ICE restart once sent to the remote peer over your signaling mechanism. Restarting ICE essentially resets ICE so that it creates all new candidates using new credentials. Existing media transmissions continue uninterrupted during this process.

For details about how ICE restart works, see [ICE restart](../webrtc_api/session_lifetime#ice_restart) in [Lifetime of a WebRTC session](../webrtc_api/session_lifetime) and [RFC 5245, section 9.1.1.1: ICE specification](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).

Example
-------

This example creates a handler for the [`iceconnectionstatechange`](iceconnectionstatechange_event) event that handles a transition to the `failed` state by restarting ICE in order to try again.

    pc.addEventListener("iceconnectionstatechange", event => {
      if (pc.iceConnectionState === "failed") {
        /* possibly reconfigure the connection in some way here */
        /* then request ICE restart */
        pc.restartIce();
      }
    });

With this code in place, a transition to the `failed` state during ICE negotiation will cause a [`negotiationneeded`](negotiationneeded_event) event to be fired, in response to which your code should renegotiate as usual. However, because you have called `restartIce()`, your call to [`createOffer()`](createoffer) which occurs in the handler for `negotiationneeded` will trigger an ICE restart rather than just a regular renegotiation.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcpeerconnection-restartice">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCPeerConnection.restartIce()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`restartIce`

77

79

70

No

No

14.1

77

77

No

55

14.5

12.0

See also
--------

-   [WebRTC API](../webrtc_api)
-   [Lifetime of a WebRTC session](../webrtc_api/session_lifetime)
-   [Signaling and video calling](../webrtc_api/signaling_and_video_calling)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/restartIce" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/restartIce</a>
