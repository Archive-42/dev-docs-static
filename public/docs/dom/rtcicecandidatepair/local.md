# RTCIceCandidatePair.local

The `local` property of the **[`RTCIceCandidatePair`](../rtcicecandidatepair)** dictionary specifies the [`RTCIceCandidate`](../rtcicecandidate) which describes the configuration of the local end of a viable WebRTC connection.

## Syntax

    localCandidate = RTCIceCandidatePair.local;

### Value

An [`RTCIceCandidate`](../rtcicecandidate) which describes the configuration of the local end of a viable pair of ICE candidates. The `RTCIceCandidatePair` is returned by the [`RTCIceTransport`](../rtcicetransport) method [`getSelectedCandidatePair()`](../rtcicetransport/getselectedcandidatepair).

## Example

This one-line example obtains the current candidate pair and then from that gets the local candidate.

    var candidatePair = pc.getSenders()[0].transport.transport.getSelectedCandidatePair();
    var localCandidate = candidatePair.local;

The [`RTCIceTransport`](../rtcicetransport) is found by getting the list of [`RTCRtpSender`](../rtcrtpsender) objects for the [`RTCPeerConnection`](../rtcpeerconnection) `pc`. In the first `RTCRtpSender`, we get the [`RTCDtlsTransport`](../rtcdtlstransport) over which the media data is being transmitted and finally, from that, the `RTCIceTransport`.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcicecandidatepair-local">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceCandidatePair.local' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.RTCIceCandidatePair.local`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePair/local" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePair/local</a>
