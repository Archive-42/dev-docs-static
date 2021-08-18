RTCIceTransport.gatheringState
==============================

The read-only **[`RTCIceTransport`](../rtcicetransport)** property `gatheringState` returns a [`DOMString`](../domstring) from the enumerated type [`RTCIceGathererState`](../rtcicegathererstate) that indicates what gathering state the ICE agent is currently in: `"new"`, `"gathering"`, or `"complete"`.

Syntax
------

    gatherState = RTCIceTransport.gatheringState;

### Value

A string from the [`RTCIceGathererState`](../rtcicegathererstate) enumerated type whose value indicates the current state of the ICE agent's candidate gathering process:

`"new"`  
The [`RTCIceTransport`](../rtcicetransport) is newly created and has not yet started to gather ICE candidates.

`"gathering"`  
The transport is in the process of gathering candidates.

`"complete"`  
The transport has finished gathering ICE candidates and has sent the end-of-candidates indicator to the remote device. The transport won't gather any further candidates unless an [ICE restart](../webrtc_api/session_lifetime#ice_restart) occurs, at which point the gathering process starts over from scratch.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-icetransport-gatheringstate">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceTransport.gatheringState' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`gatheringState`

75

79

No

No

62

11

75

75

No

54

11

11.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/gatheringState" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/gatheringState</a>
