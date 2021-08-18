RTCIceTransport
===============

The `RTCIceTransport` interface provides access to information about the [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) transport layer over which the data is being sent and received. This is particularly useful if you need to access state information about the connection.

Properties
----------

*The `RTCIceTransport` interface inherits properties from its parent, [`EventTarget`](eventtarget). It also offers the following properties:*

 [`component`](rtcicetransport/component) <span class="badge inline readonly">Read only </span>   
The ICE component being used by the transport. The value is one of the strings from the [`RTCIceTransport`](rtcicetransport) enumerated type: `"RTP"` or `"RTSP"`.

 [`gatheringState`](rtcicetransport/gatheringstate) <span class="badge inline readonly">Read only </span>   
A [`DOMString`](domstring) indicating which gathering state the ICE agent is currently in. The value is one of those included in the [`RTCIceGathererState`](rtcicegathererstate) enumerated type: `"new"`, `"gathering"`, or `"complete"`.

 [`role`](rtcicetransport/role) <span class="badge inline readonly">Read only </span>   
Returns a [`DOMString`](domstring) whose value is one of the members of the [`RTCIceRole`](rtcicerole) enumerated type: `"controlling"` or `"controlled"`; this indicates whether the ICE agent is the one that makes the final decision as to the candidate pair to use or not.

 [`state`](rtcicetransport/state) <span class="badge inline readonly">Read only </span>   
A [`DOMString`](domstring) indicating what the current state of the ICE agent is. The value of `state` can be used to determine whether the ICE agent has made an initial connection using a viable candidate pair (`"connected"`), made its final selection of candidate pairs (`"completed"`), or in an error state (`"failed"`), among other states. See the [`RTCIceTransportState`](rtcicetransportstate) enumerated type for a complete list of states.

Methods
-------

*Also includes methods from [`EventTarget`](eventtarget), the parent interface.*

[`getLocalCandidates()`](rtcicetransport/getlocalcandidates)  
Returns an array of [`RTCIceCandidate`](rtcicecandidate) objects, each describing one of the ICE candidates that have been gathered so far for the local device. These are the same candidates which have already been sent to the remote peer by sending an `icecandidate` event to the [`RTCPeerConnection`](rtcpeerconnection) for transmission.

[`getLocalParameters()`](rtcicetransport/getlocalparameters)  
Returns a [`RTCIceParameters`](rtciceparameters) object describing the ICE parameters established by a call to the [`RTCPeerConnection.setLocalDescription()`](rtcpeerconnection/setlocaldescription) method. Returns `null` if parameters have not yet been received.

[`getRemoteCandidates()`](rtcicetransport/getremotecandidates)  
Returns an array of [`RTCIceCandidate`](rtcicecandidate) objects, one for each of the remote device's ICE candidates that have been received by the local end of the [`RTCPeerConnection`](rtcpeerconnection) and delivered to ICE by calling [`addIceCandidate()`](rtcpeerconnection/addicecandidate).

[`getRemoteParameters()`](rtcicetransport/getremoteparameters)  
Returns a [`RTCIceParameters`](rtciceparameters) object containing the ICE parameters for the remote device, as set by a call to [`RTCPeerConnection.setRemoteDescription()`](rtcpeerconnection/setremotedescription). If `setRemoteDescription()` hasn't been called yet, the return value is `null`.

[`getSelectedCandidatePair()`](rtcicetransport/getselectedcandidatepair)  
Returns a [`RTCIceCandidatePair`](rtcicecandidatepair) object that identifies the two candidates—one for each end of the connection—that have been selected so far. It's possible that a better pair will be found and selected later; if you need to keep up with this, watch for the `selectedcandidatepairchange` event. If no candidate pair has been selected yet, the return value is `null`.

Events
------

Listen to these events using [`addEventListener()`](eventtarget/addeventlistener) or by assigning an event listener to the `oneventname` property of this interface.

[`gatheringstatechange`](rtcicetransport/gatheringstatechange_event)  
Sent to the [`RTCIceTransport`](rtcicetransport) object to indicate that the value of the [`gatheringState`](rtcicetransport/gatheringstate) property has changed, indicating a change in this transport's ICE candidate negotiation process.  
Also available through the [`ongatheringstatechange`](rtcicetransport/ongatheringstatechange) event handler property.

[`selectedcandidatepairchange`](rtcicetransport/selectedcandidatepairchange_event)  
Sent to the `RTCIceTransport` when a new, better pair of candidates has been selected to describe the connectivity between the two peers. This occurs during negotiation or renegotiation, including after an ICE restart, which reuses the existing `RTCIceTransport` objects. The current candidate pair can be obtained using [`getSelectedCandidatePair()`](rtcicetransport/getselectedcandidatepair).  
Also available using the [`onselectedcandidatepairchange`](rtcicetransport/onselectedcandidatepairchange) event handler property.

[`statechange`](rtcicetransport/statechange_event)  
Sent to the `RTCIceTransport` instance when the value of the [`state`](rtcicetransport/state) property has changed, indicating that the ICE gathering process has changed state.  
Also available through the [`onstatechange`](rtcicetransport/onstatechange) event handler property.

Examples
--------

tbd

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcicetransport">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceTransport' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`RTCIceTransport`

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

`RTCIceTransport`

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

`addRemoteCandidate`

No

13-79

No

No

No

No

No

No

No

No

No

No

`component`

No

13-79

No

No

No

No

No

No

No

No

No

No

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

`gatheringstatechange_event`

No

No

No

No

No

No

No

No

No

No

No

No

`getLocalCandidates`

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

`getLocalParameters`

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

`getRemoteCandidates`

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

`getRemoteParameters`

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

`getSelectedCandidatePair`

75

79

13-79

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

`onselectedcandidatepairchange`

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

`onstatechange`

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

`selectedcandidatepairchange_event`

No

No

No

No

No

No

No

No

No

No

No

No

`start`

No

13-79

No

No

No

No

No

No

No

No

No

No

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

`statechange_event`

No

No

No

No

No

No

No

No

No

No

No

No

`stop`

No

13-79

No

No

No

No

No

No

No

No

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport</a>
