# RTCIceCandidatePair.remote

The `remote` property of the **[`RTCIceCandidatePair`](../rtcicecandidatepair)** dictionary specifies the [`RTCIceCandidate`](../rtcicecandidate) describing the configuration of the remote end of a viable WebRTC connection.

## Syntax

    remoteCandidate = RTCIceCandidatePair.remote;

### Value

An [`RTCIceCandidate`](../rtcicecandidate) which describes the configuration of the remote end of a viable pair of ICE candidates. The `RTCIceCandidatePair` is returned by the [`RTCIceTransport`](../rtcicetransport) method [`getSelectedCandidatePair()`](../rtcicetransport/getselectedcandidatepair).

## Example

This one-line example obtains the current candidate pair and then from that gets the remote candidate.

    var candidatePair = pc.getSenders()[0].transport.transport.getSelectedCandidatePair();
    var remoteCandidate = candidatePair.remote;

The [`RTCIceTransport`](../rtcicetransport) is found by getting the list of [`RTCRtpSender`](../rtcrtpsender) objects for the [`RTCPeerConnection`](../rtcpeerconnection) `pc`. In the first `RTCRtpSender`, we get the [`RTCDtlsTransport`](../rtcdtlstransport) over which the media data is being transmitted and finally, from that, the `RTCIceTransport`.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcicecandidatepair-remote">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceCandidatePair.remote' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.RTCIceCandidatePair.remote`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePair/remote" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePair/remote</a>
