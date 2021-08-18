# RTCIceTransport.onselectedcandidatepairchange

The [`RTCIceTransport`](../rtcicetransport) interface's `onselectedcandidatepairchange` event handler specifies a function to be called to handle the `selectedcandidatepairchange` event, which is fired when the ICE agent selects a new candidate pair to be used for the connection.

## Syntax

    RTCIceTransport.onselectedcandidatepairchange = candidatePairHandler;

### Value

This propoerty should be set to reference an event handler function to be called by the ICE agent when it discovers a new candidate pair that the [`RTCIceTransport`](../rtcicetransport) will be using for communication with the remote peer. This event will occur at least once, and may occur more than once if the ICE agent continues to identify candidate pairs that will work better, more closely match the requested parameters, and so forth.

The event handler can determine the current state by calling the transport's [`getSelectedCandidatePair()`](getselectedcandidatepair) method, which returns a [`RTCIceCandidatePair`](../rtcicecandidatepair) whose [`RTCIceCandidatePair.local`](../rtcicecandidatepair/local) and <span class="page-not-created">`RTCIceCandidatePair.global`</span> properties specify [`RTCIceCandidate`](../rtcicecandidate) objects describing the local and remote candidates that are currently being used.

## Example

In this example, an event handler for `selectedcandidatepairchange` is set up to update an on-screen display showing the protocol used by the currently selected candidate pair.

    var iceTransport = pc.getSenders()[0].transport.iceTransport;
    var localProto = document.getElementById("local-protocol");
    var remoteProto = document.getElementById("remote-protocol");

    iceTransport.onselectedcandidatepairchange = function(event) {
      var pair = iceTransport.getSelectedCandidatePair();
      localProtocol.innerText = pair.local.protocol.toUpperCase();
      remoteProtocol.innerText = pair.remote.protocol.toUpperCase();
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcicetransport-onselectedcandidatepairchange">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceTransport.onselectedcandidatepairchange' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

## Browser compatibility

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

`onselectedcandidatepairchange`

75

79

No

No

62

No

75

75

No

54

No

11.0

## See also

- The `selectedcandidatepair` event and its type, [`Event`](../event).
- The other event handlers for `RTCIceTransport`: [`onstatechange`](onstatechange) and[`ongatheringstatechange`](ongatheringstatechange)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/onselectedcandidatepairchange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/onselectedcandidatepairchange</a>
