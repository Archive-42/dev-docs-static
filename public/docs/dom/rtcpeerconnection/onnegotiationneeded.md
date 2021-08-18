RTCPeerConnection.onnegotiationneeded
=====================================

The [`RTCPeerConnection`](../rtcpeerconnection) interface's `onnegotiationneeded` property is an [`EventListener`](../eventlistener) which specifies a function which is called to handle the `negotiationneeded` event when it occurs on an [`RTCPeerConnection`](../rtcpeerconnection) instance. This event is fired when a change has occurred which requires session negotiation. This negotiation should be carried out as the offerer, because some session changes cannot be negotiated as the answerer.

Most commonly, the `negotiationneeded` event is fired after a send track is added to the [`RTCPeerConnection`](../rtcpeerconnection). If the session is modified in a manner that requires negotiation while a negotiation is already in progress, no `negotiationneeded` event will fire until negotiation completes, and only then if negotiation is still needed.

Syntax
------

    RTCPeerConnection.onnegotiationneeded = eventHandler;

### Value

This should be set to a function you provide which is passed a single parameter: an [`Event`](../event) object containing the `negotiationneeded` event. There's no additional information provided in the event; anything you need, you can get by examining the [properties of the `RTCPeerConnection`](../rtcpeerconnection#properties).

Example
-------

This example, derived from the example in [Signaling and video calling](../webrtc_api/signaling_and_video_calling), establishes a handler for `negotiationneeded` events to handle creating an offer, configuring the local end of the connection, and sending the offer to the remote peer.

    pc.onnegotiationneeded = function() {
      pc.createOffer().then(function(offer) {
        return pc.setLocalDescription(offer);
      })
      .then(function() {
          // Send the offer to the remote peer through the signaling server
        });
      })
      .catch(reportError);
    }

First, it creates the offer by calling [`createOffer()`](createoffer). When that succeeds, the offer is passed into [`setLocalDescription()`](setlocaldescription) to set the local description for the connection. Once that's succeeded in turn, the offer can be sent to the signaling server for delivery to the remote peer.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcpeerconnection-onnegotiationneeded">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCPeerConnection.onnegotiationneeded' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`onnegotiationneeded`

24

15

22

No

43

Promise-based version.

37-43

11

≤37

Yes

44

43

Promise-based version.

37-43

11

6.0

See also
--------

-   The `negotiationneeded` event and its type, [`Event`](../event).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/onnegotiationneeded" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/onnegotiationneeded</a>
