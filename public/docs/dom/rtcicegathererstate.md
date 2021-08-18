# RTCIceGathererState

The `RTCIceGathererState` enumerated type provides the string values which can be returned by an [`RTCIceTransport`](rtcicetransport) object's [`gatheringState`](rtcicetransport/gatheringstate).

## Values

`"new"`  
The [`RTCIceTransport`](rtcicetransport) is newly created and has not yet started to gather ICE candidates.

`"gathering"`  
The transport is in the process of gathering candidates.

`"complete"`  
The transport has finished gathering ICE candidates and has sent the end-of-candidates indicator to the remote device. The transport won't gather any further candidates unless an [ICE restart](webrtc_api/session_lifetime#ice_restart) occurs, at which point the gathering process starts over from scratch.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcicegathererstate">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceGathererState' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.RTCIceGathererState`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceGathererState" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceGathererState</a>
