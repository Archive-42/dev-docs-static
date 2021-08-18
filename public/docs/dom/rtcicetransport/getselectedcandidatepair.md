# RTCIceTransport.getSelectedCandidatePair()

The [`RTCIceTransport`](../rtcicetransport) method `getSelectedCandidatePair()` returns an [`RTCIceCandidatePair`](../rtcicecandidatepair) object containing the current best-choice pair of [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) candidates describing the configuration of the endpoints of the transport.

## Syntax

    candidatePair = RTCIceTransport.getSelectedCandidatePair();

### Parameters

None.

### Return value

A [`RTCIceCandidatePair`](../rtcicecandidatepair) object describing the configurations of the currently-selected candidate pair's two endpoints. [`local`](../rtcicecandidatepair/local) describes the configuration of the local end of the connection, while [`remote`](../rtcicecandidatepair/remote) describes the remote peer's configuration.

The return value is `null` if no pair of candidates has been selected yet.

## Usage notes

As the ICE agent performs negotiation of a [`RTCPeerConnection`](../rtcpeerconnection), it gathers and analyzes candidate configurations from each the two peers. As soon as it finds an acceptable matching pair of candidates, meeting the requirements for the connection, a `selectedcandidatepairchange` event is fired at the [`RTCIceTransport`](../rtcicetransport). From that time forward, the best matching pair of candidates will always be available by calling `getSelectedCandidatePair()`.

As ICE negotiation continues, any time a pair of candidates is discovered that is better than the currently-selected pair, the new pair is selected, replacing the previous pairing, and the `selectedcandidatepairchange` event is fired again.

**Note:** It's possible for one of the configurations in the selected candidate pair to remain unchanged when a new pairing is chosen.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcicetransport-getselectedcandidatepair">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceTransport.getSelectedCandidatePair()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`getSelectedCandidatePair`

75

79

13-79

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/getSelectedCandidatePair" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/getSelectedCandidatePair</a>
