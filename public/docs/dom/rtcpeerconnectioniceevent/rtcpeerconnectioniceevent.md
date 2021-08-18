RTCPeerConnectionIceEvent()
===========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `RTCPeerConnectionIceEvent()` constructor creates a new [`RTCPeerConnectionIceEvent`](../rtcpeerconnectioniceevent).

Syntax
------

     var event = new RTCPeerConnectionIceEvent(type, options);

### Parameters

`type`  
Is a [`DOMString`](../domstring) containing the name of the event, like `"icecandidate"`.

`options`  
A dictionary of type `RTCPeerConnectionInit`, which may contain one or more of the following fields:

-   `"candidate"` (optional, default is `null`): A [`RTCIceCandidate`](../rtcicecandidate) representing the ICE candidate being concerned by the event. If `null`, the event indicates the end of candidate gathering.
-   `"url"` (optional, default is `null`): The URL of the STUN or TURN server which was used to gather the candidate. If the candidate was not gathered by a [STUN](https://developer.mozilla.org/en-US/docs/Glossary/STUN) or [TURN](https://developer.mozilla.org/en-US/docs/Glossary/TURN) server, this value must be `null`.
-   `"bubbles"` (optional, default is `false`): Inherited from `EventInit()`, this Boolean option indicates whether or not the event must bubble.
-   `"cancelable"` (optional, default is `false`, inherited from `EventInit()`, this Boolean indicates whether or not the event can be canceled.

### Return value

A newly-created [`RTCPeerConnectionIceEvent`](../rtcpeerconnectioniceevent), configured as specified in the provided options.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcpeerconnectioniceevent-constructor">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCPeerConnectionIceEvent()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`RTCPeerConnectionIceEvent`

56

≤18

Yes

No

Yes

12

56

56

Yes

Yes

12

6.0

See also
--------

-   [WebRTC](../webrtc_api)
-   Its usual target: [`RTCPeerConnection`](../rtcpeerconnection).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnectionIceEvent/RTCPeerConnectionIceEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnectionIceEvent/RTCPeerConnectionIceEvent</a>
