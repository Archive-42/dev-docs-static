# RTCIceProtocol

The [WebRTC API's](webrtc_api) `RTCIceProtocol` enumerated type provides a set of [`DOMString`](domstring) values representing the names of the transport protocols ICE candidates can use. These strings are taken directly from the `candidate` a-line in SDP.

## Values

`tcp`  
The candidate, if selected, would use [TCP](https://developer.mozilla.org/en-US/docs/Glossary/TCP) as the transport protocol for its data. The [`tcpType`](rtcicecandidate/tcptype) property provides additional information about the kind of TCP candidate represented by the object.

`udp`  
The candidate will use the [UDP](https://developer.mozilla.org/en-US/docs/Glossary/UDP) transport protocol for its data. This is the preferred protocol for media interactions because of its better performance profile.

## Usage notes

The `RTCIceProtocol` type is used by the [`protocol`](rtcicecandidate/protocol) property of [`RTCIceCandidate`](rtcicecandidate) objects.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#rtciceprotocol">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceProtocol' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.RTCIceProtocol`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceProtocol" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceProtocol</a>
