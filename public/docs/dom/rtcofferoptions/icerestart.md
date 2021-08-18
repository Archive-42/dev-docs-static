RTCOfferOptions.iceRestart
==========================

The `iceRestart` property of the **[`RTCOfferOptions`](../rtcofferoptions)** dictionary is a Boolean value which, when `true`, tells the [`RTCPeerConnection`](../rtcpeerconnection) to start ICE renegotiation.

**Note:** Rather than manually creating and submitting an offer with `iceRestart` set to `true`, you should consider calling the [`RTCPeerConnection`](../rtcpeerconnection) method [`restartIce()`](../rtcpeerconnection/restartice) instead.

Syntax
------

    var options = {
      iceRestart: trueOrFalse
    };

### Value

A Boolean value indicating whether or not the `RTCPeerConnection` should generate new values for the connection's ice-ufrag and ice-pwd values, which will trigger ICE renegotiation on the next message sent to the remote peer.

Usage notes
-----------

When the [`RTCPeerConnection`](../rtcpeerconnection) object's ICE connection state changes to `failed`, you should try to trigger an [ICE restart](../webrtc_api/session_lifetime#ice_restart). You should ideally do this by calling the [`RTCPeerConnection`](../rtcpeerconnection)'s [`restartIce()`](../rtcpeerconnection/restartice) method, if it's available.

Fundamentally, this renegotiation is triggered by generating and using new values for the ICE username fragment ("ufrag")}}

Example
-------

This example shows a handler for the `iceconnectionstatechange` event. It watches for the ICE connection state to transition to `"failed"`, which indicates that an ICE restart should be tried in order to attempt to bring the connection back up.

    pc.oniceconnectionstatechange = function(evt) {
      if (pc.iceConnectionState === "failed") {
        if (pc.restartIce) {
          pc.restartIce();
        } else {
          pc.createOffer({ iceRestart: true })
          .then(pc.setLocalDescription)
          .then(sendOfferToServer);
        }
      }
    }

If the state changes to `failed`, this handler starts by looking to see if the [`RTCPeerConnection`](../rtcpeerconnection) includes the [`restartIce()`](../rtcpeerconnection/restartice) method; if it does, we call that to request an ICE restart. Otherwise, we call back to the older technique: we manually create a new offer with `iceRestart` set to `true`, then that offer is set as the new local description for the connection. After that, the offer is sent to the server by calling a custom function `sendOfferToServer()`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcofferoptions-icerestart">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCOfferOptions.iceRestart' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`iceRestart`

50

≤79

48

No

?

?

50

50

48

?

?

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCOfferOptions/iceRestart" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCOfferOptions/iceRestart</a>
