RTCPeerConnectionIceEvent.candidate
===================================

The read-only `candidate` property of the [`RTCPeerConnectionIceEvent`](../rtcpeerconnectioniceevent) interface returns the [`RTCIceCandidate`](../rtcicecandidate) associated with the event.

Syntax
------

     var candidate = event.candidate;

### Value

An [`RTCIceCandidate`](../rtcicecandidate) object representing the ICE candidate that has been received, or `null` to indicate that there are no further candidates for this negotiation session.

Example
-------

    pc.onicecandidate = function( ev ) {
      alert("The ICE candidate (transport address: '" +
        ev.candidate.candidate +
        "') has been added to this connection.");
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcpeerconnectioniceevent-candidate">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCPeerConnectionIceEvent.candidate' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

See also
--------

-   `icecandidate`
-   [`RTCPeerConnection`](../rtcpeerconnection)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnectionIceEvent/candidate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnectionIceEvent/candidate</a>
