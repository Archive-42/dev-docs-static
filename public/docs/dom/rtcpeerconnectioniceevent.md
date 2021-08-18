RTCPeerConnectionIceEvent
=========================

The `RTCPeerConnectionIceEvent` interface represents events that occurs in relation to [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) candidates with the target, usually an [`RTCPeerConnection`](rtcpeerconnection). Only one event is of this type: `icecandidate`.

Properties
----------

*A [`RTCPeerConnectionIceEvent`](rtcpeerconnectioniceevent) being an [`Event`](event), this event also implements these properties*.

 [`RTCPeerConnectionIceEvent.candidate`](rtcpeerconnectioniceevent/candidate) <span class="badge inline readonly">Read only </span>   
Contains the [`RTCIceCandidate`](rtcicecandidate) containing the candidate associated with the event, or `null` if this event indicates that there are no further candidates to come.

Constructors
------------

[`RTCPeerConnectionIceEvent()`](rtcpeerconnectioniceevent/rtcpeerconnectioniceevent)  
Returns a new `RTCPeerConnectionIceEvent`. It takes two parameters, the first being a [`DOMString`](domstring) representing the type of the event; the second a dictionary containing the [`RTCIceCandidate`](rtcicecandidate) it refers to.

Methods
-------

*A [`RTCPeerConnectionIceEvent`](rtcpeerconnectioniceevent) being an [`Event`](event), this event also implements these properties. There is no specific [`RTCDataChannelEvent`](rtcdatachannelevent) method.*

Examples
--------

    pc.onicecandidate = function( ev ) {
      alert("The ICE candidate (transport address: '" +
        ev.candidate.candidate +
        "') has been added to this connection.");
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#rtcpeerconnectioniceevent">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCPeerConnectionIceEvent' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

Yes-56

56

≤18

Yes

No

Yes

12

Yes-56

56

Yes-56

56

Yes

Yes

12

Yes-6.0

6.0

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

`candidate`

56

15

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

`url`

No

No

?

No

?

12

No

No

?

?

12

No

See also
--------

-   [WebRTC](webrtc_api)
-   Its usual target: [`RTCPeerConnection`](rtcpeerconnection).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnectionIceEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnectionIceEvent</a>
