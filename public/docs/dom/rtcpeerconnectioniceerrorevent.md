RTCPeerConnectionIceErrorEvent
==============================

The `RTCPeerConnectionIceErrorEvent` interface—based upon the [`Event`](event) interface—provides details pertaining to an [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) error announced by sending an [`icecandidateerror`](rtcpeerconnection/icecandidateerror_event) event to the [`RTCPeerConnection`](rtcpeerconnection) object.

Constructor
-----------

<span class="page-not-created">`RTCPeerConnectionIceErrorEvent()`</span>  
Creates and returns a new `RTCPeerConnectionIceErrorEvent` object, with its `type` and other properties initialized as specified in the parameters. You will not normally create an object of this type yourself.

Properties
----------

*The `RTCPeerConnectionIceErrorEvent` interface includes the properties found on the [`Event`](event) interface, as well as the following properties:*

 [`address`](rtcpeerconnectioniceerrorevent/address) <span class="badge inline readonly">Read only </span>   
A [`DOMString`](domstring) providing the local IP address used to communicate with the [STUN](https://developer.mozilla.org/en-US/docs/Glossary/STUN) or [TURN](https://developer.mozilla.org/en-US/docs/Glossary/TURN) server being used to negotiate the connection, or `null` if the local IP address has not yet been exposed as part of a local ICE candidate.

 <span class="page-not-created">`errorCode`</span> <span class="badge inline readonly">Read only </span>   
An unsigned integer value stating the numeric [STUN error code](https://www.iana.org/assignments/stun-parameters/stun-parameters.xhtml#stun-parameters-6) returned by the STUN or TURN server. If no host candidate can reach the server, this property is set to the number 701, which is outside the range of valid STUN error codes. The 701 error is fired only once per server URL, and only while the is [`icegatheringstate`](rtcpeerconnection/icegatheringstate) is `gathering`.

 <span class="page-not-created">`errorText`</span> <span class="badge inline readonly">Read only </span>   
A [`DOMString`](domstring) containing the STUN reason text returned by the STUN or TURN server. If communication with the STUN or TURN server couldn't be established at all, this string will be a browser-specific string explaining the error.

 <span class="page-not-created">`port`</span> <span class="badge inline readonly">Read only </span>   
An unsigned integer value giving the port number over which communication with the STUN or TURN server is taking place, using the IP address given in `address`. `null` if the connection hasn't been established (that is, if `address` is `null`).

 <span class="page-not-created">`url`</span> <span class="badge inline readonly">Read only </span>   
A [`DOMString`](domstring) indicating the URL of the STUN or TURN server with which the error occurred.

Methods
-------

*`RTCPeerConnectionIceErrorEvent` has no methods other than any provided by the parent interface, [`Event`](event).*

Examples
--------

TBD

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#rtcpeerconnectioniceerrorevent">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCPeerConnectionIceErrorEvent' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`RTCPeerConnectionIceErrorEvent`

?

?

?

No

?

14.1

?

?

?

?

14.5

?

`errorCode`

?

?

?

No

?

14.1

?

?

?

?

14.5

?

`errorText`

?

?

?

No

?

14.1

?

?

?

?

14.5

?

`hostCandidate`

?

?

?

No

?

No

?

?

?

?

No

?

`url`

?

?

?

No

?

14.1

?

?

?

?

14.5

?

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnectionIceErrorEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnectionIceErrorEvent</a>
