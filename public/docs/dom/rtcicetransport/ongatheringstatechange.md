# RTCIceTransport.ongatheringstatechange

The `ongatheringstatechange` event handler for the [`RTCIceTransport`](../rtcicetransport) interface specifies an event handler that is to be called when the `gatheringstatechange` event occurs on the transport. This event is delivered whenever the transport's [`gatheringState`](gatheringstate) property changes.

## Syntax

    RTCIceTransport.ongatheringstatechange = stateChangeHandler;

### Value

A function to be called when the [`RTCIceTransport`](../rtcicetransport) object's gathering state changes. To determine the new state, examine the value of [`gatheringState`](gatheringstate).

The gathering state indicates whether or not the ICE agent has begun gathering candidates, and if so, whether or not gathering has finished. Its possible values are:

`"new"`  
The [`RTCIceTransport`](../rtcicetransport) is newly created and has not yet started to gather ICE candidates.

`"gathering"`  
The transport is in the process of gathering candidates.

`"complete"`  
The transport has finished gathering ICE candidates and has sent the end-of-candidates indicator to the remote device. The transport won't gather any further candidates unless an [ICE restart](../webrtc_api/session_lifetime#ice_restart) occurs, at which point the gathering process starts over from scratch.

## Example

This snippet establishes a handler for the `gatheringstatechange` event that checks to see if the state has changed to `"complete"`, indicating that all ICE candidates from both the local and remote peers have been received and processed.

    var iceTransport = pc.getSenders()[0].transport.transport;

    iceTransport.ongatheringstatechange = function(event) {
      if (iceTransport.gatheringState == "complete") {
        allCandidatesReceived(pc);
      }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcicetransport-ongatheringstatechange">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceTransport.ongatheringstatechange' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`ongatheringstatechange`

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

- The `gatheringstatechange` event and its type, [`Event`](../event).
- The other event handlers for `RTCIceTransport`: [`onstatechange`](onstatechange) and [`onselectedcandidatepairchange`](onselectedcandidatepairchange)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/ongatheringstatechange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/ongatheringstatechange</a>
