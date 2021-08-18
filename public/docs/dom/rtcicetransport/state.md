RTCIceTransport.state
=====================

The read-only **[`RTCIceTransport`](../rtcicetransport)** property `state` returns the current state of the ICE transport, so you can determine the state of ICE gathering in which the ICE agent currently is operating.

This differs from the [`gatheringState`](gatheringstate), which only indicates whether or not ICE gathering is currently underway.

Syntax
------

    iceState = iceTransport.state;

### Value

A [`DOMString`](../domstring), whose value is one of those found in the enumerated type [`RTCIceTransportState`](../rtcicetransportstate), which indicates the stage of ICE gathering that's currently underway. Its value will be one of the following:

`"new"`  
The [`RTCIceTransport`](../rtcicetransport) is currently gathering local candidates, or is waiting for the remote device to begin to transmit the remote candidates, or both. In this state, checking of candidates to look for those which might be acceptable has not yet begun.

`"checking"`  
At least one remote candidate has been received, and the `RTCIceTransport` has begun examining pairings of remote and local candidates in order to attempt to identify viable pairs that could be used to establish a connection. Keep in mind that gathering of local candidates may still be underway, and, similarly, the remote device also may still be gathering candidates of its own.

`"connected"`  
A viable candidate pair has been found and selected, and the `RTCIceTransport` has connected the two peers together using that pair. However, there are still candidates pairings to consider, and there may still be gathering underway on one or both of the two devices.

The transport may revert from the `"connected"` state to the `"checking"` state if either peer decides to cancel consent to use the selected candidate pair, and may revert to `"disconnected"` if there are no candidates left to check but one or both clients are still gathering candidates.

`"completed"`  
The transport has finished gathering local candidates and has received a notification from the remote peer that no more candidates will be sent. In addition, all candidate pairs have been considered and a pair has been selected for use. If consent checks fail on all successful candidate pairs, the transport state will change to `"failed"`.

`"disconnected"`  
The ICE agent has determined that connectivity has been lost for this [`RTCIceTransport`](../rtcicetransport). This is not a failure state (that's `"failed"`). A value of `"disconnected"` means that a transient issue has occurred that has broken the connection, but that should resolve itself automatically without your code having to take any action. See [The disconnected state](#the_disconnected_state) for additional details.

`"failed"`  
The `RTCIceTransport` has finished the gathering process, has received the "no more candidates" notification from the remote peer, and has finished checking pairs of candidates, without successfully finding a pair that is both valid and for which consent can be obtained. *This is a terminal state, indicating that the connection cannot be achieved or maintained.*

`"closed"`  
The transport has shut down and is no longer responding to STUN requests.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#rtcicetransportstate">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceTransportState' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`state`

75

13

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/state" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/state</a>
