RTCPeerConnection.iceGatheringState
===================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The read-only property `RTCPeerConnection.iceGatheringState` returns an enum of type `RTCIceGatheringState` that describes connection's ICE gathering state. This lets you detect, for example, when collection of ICE candidates has finished.

You can detect when the value of this property changes by watching for an event of type `icegatheringstatechange`.

Syntax
------

     var state = RTCPeerConnection.iceGatheringState;

### Value

The possible values are those of an enum of type `RTCIceGatheringState`.

### RTCIceGatheringState enum

The `RTCIceGatheringState` enum defines string constants which reflect the current status of ICE gathering, as returned using the [`RTCPeerConnection.iceGatheringState`](icegatheringstate) property. You can detect when this value changes by watching for an event of type `icegatheringstatechange`.

<table><thead><tr class="header"><th>Constant</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>"new"</code></td><td>The peer connection was just created and hasn't done any networking yet.</td></tr><tr class="even"><td><code>"gathering"</code></td><td>The ICE agent is in the process of gathering candidates for the connection.</td></tr><tr class="odd"><td><code>"complete"</code></td><td>The ICE agent has finished gathering candidates. If something happens that requires collecting new candidates, such as a new interface being added or the addition of a new ICE server, the state will revert to "gathering" to gather those candidates.</td></tr></tbody></table>

Example
-------

    var pc = new RTCPeerConnection();
    var state = pc.iceGatheringState;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-peerconnection-ice-gathering-state">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCPeerConnection.iceGatheringState' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`iceGatheringState`

25

15

22

No

43

Promise-based version.

37-43

11

≤37

25

44

43

Promise-based version.

37-43

11

6.0

See also
--------

-   `icegatheringstatechange`
-   [WebRTC](../webrtc_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/iceGatheringState" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/iceGatheringState</a>
