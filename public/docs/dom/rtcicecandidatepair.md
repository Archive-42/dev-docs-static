# RTCIceCandidatePair

The `RTCIceCandidatePair` dictionary describes a pair of ICE candidates which together comprise a description of a viable connection between two WebRTC endpoints. It is used as the return value from [`RTCIceTransport.getSelectedCandidatePair()`](rtcicetransport/getselectedcandidatepair) to identify the currently-selected candidate pair identified by the ICE agent.

## Properties

[`local`](rtcicecandidatepair/local)  
An [`RTCIceCandidate`](rtcicecandidate) describing the configuration of the local end of the connection.

[`remote`](rtcicecandidatepair/remote)  
The `RTCIceCandidate` describing the configuration of the remote end of the connection.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#rtcicecandidatepair">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceCandidatePair' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.RTCIceCandidatePair`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePair" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePair</a>
