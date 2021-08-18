RTCIceTransport.role
====================

The read-only **[`RTCIceTransport`](../rtcicetransport)** property `role` indicates which [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) role the transport is fulfilling: that of the controlling agent, or the agent that is being controlled.

You can learn more about ICE roles in [Choosing a candidate pair](#) in [WebRTC connectivity](../webrtc_api/connectivity).

Syntax
------

    iceRole = RTCIceTransport.role;

### Value

A [`DOMString`](../domstring) specifying whether the [`RTCIceTransport`](../rtcicetransport) represents the controlling agent or the controlled agent. The value must be one of those found in the enumerated type [`RTCIceRole`](../rtcicerole):

`"controlling"`  
The [`RTCIceTransport`](../rtcicetransport) object is serving as the controlling agent.

`"controlled"`  
The transport is the controlled agent.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-icetransport-role">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceTransport.role' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`role`

75

13

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/role" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/role</a>
