# RTCIceCandidate.type

The **[`RTCIceCandidate`](../rtcicecandidate)** interface's read-only `type` specifies the type of candidate the object represents.

The `type` field's value is set when the [`RTCIceCandidate()`](rtcicecandidate) constructor is used. You can't specify the value of `type` in the options object, but the address is automatically extracted from the [`candidate`](../rtcicecandidateinit/candidate) a-line, if it's formatted properly, being taken from its `cand-type` field.

## Syntax

    var type = RTCIceCandidate.type;

### Value

A [`DOMString`](../domstring) whose value is one of those defined by the [`RTCIceCandidateType`](../rtcicecandidatetype) enumerated type.

These candidate types are listed in order of priority; the higher in the list they are, the more efficient they are.

`host`  
The candidate is a host candidate, whose IP address as specified in the [`RTCIceCandidate.ip`](address) property is in fact the true address of the remote peer.

`srflx`  
The candidate is a server reflexive candidate; the `ip` indicates an intermediary address assigned by the [STUN](https://developer.mozilla.org/en-US/docs/Glossary/STUN) server to represent the candidate's peer anonymously.

`prflx`  
The candidate is a peer reflexive candidate; the `ip` is an intermediary address assigned by the STUN server to represent the candidate's peer anonymously.

`relay`  
The candidate is a relay candidate, obtained from a [TURN](https://developer.mozilla.org/en-US/docs/Glossary/TURN) server. The relay candidate's IP address is an address the TURN server uses to forward the media between the two peers.

If `type` is `null`, that information was missing from the [`candidate`](candidate)'s a-line, which will cause [`RTCPeerConnection.addIceCandidate()`](../rtcpeerconnection/addicecandidate) to throw an `OperationError` exception.

## Example

In this example, the candidate's [`type`](type) is used to present a modified user interface for host candidates (those where the [`ip`](address) refers directly to the remote peer, rather than an intermediary).

    if (candidate.type == "host") {
      showHostControls();
    } else {
      hideHostControls();
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcicecandidate-type">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceCandidate.type' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`type`

74

79

No

No

62

14.1

74

74

No

53

14.5

11.0

## See also

- [WebRTC API](../webrtc_api)
- [Introduction to WebRTC protocols](../webrtc_api/protocols)
- [WebRTC connectivity](../webrtc_api/connectivity)
- [`RTCIceCandidate.tcpType`](tcptype)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/type" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/type</a>
