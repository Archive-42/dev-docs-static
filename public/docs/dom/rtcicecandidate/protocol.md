RTCIceCandidate.protocol
========================

The **[`RTCIceCandidate`](../rtcicecandidate)** interface's read-only `protocol` property is a string which indicates whether the candidate uses [UDP](https://developer.mozilla.org/en-US/docs/Glossary/UDP) or [TCP](https://developer.mozilla.org/en-US/docs/Glossary/TCP) as its transport protocol. `protocol` is `null` by default if not specified properly in the SDP, but this is an error condition and will result in a thrown exception when you call [`RTCPeerConnection.addIceCandidate()`](../rtcpeerconnection/addicecandidate).

The `protocol` property's value is set when the [`RTCIceCandidate()`](rtcicecandidate) constructor is used. The value is automatically extracted from the [`candidate`](../rtcicecandidateinit/candidate) a-line, if it's formatted properly.

Syntax
------

    var protocol = RTCIceCandidate.protocol;

### Value

A [`DOMString`](../domstring) which indicates what network protocol the candidate uses, UDP or TCP. These values are defined by the enumerated type [`RTCIceProtocol`](../rtciceprotocol):

`tcp`  
The candidate, if selected, would use [TCP](https://developer.mozilla.org/en-US/docs/Glossary/TCP) as the transport protocol for its data. The [`tcpType`](tcptype) property provides additional information about the kind of TCP candidate represented by the object.

`udp`  
The candidate will use the [UDP](https://developer.mozilla.org/en-US/docs/Glossary/UDP) transport protocol for its data. This is the preferred protocol for media interactions because of its better performance profile.

**Note:** If `protocol` is `null` — and `protocol` is supported by the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) — passing the candidate to [`addIceCandidate()`](../rtcpeerconnection/addicecandidate) will fail, throwing an `OperationError` exception.

Usage notes
-----------

Here's an example candidate a-line from an ICE transaction:

    a=candidate:4234997325 1 udp 2043278322 192.168.0.56 44323 typ host

The third field, `"udp"`, is the protocol type, indicating that the candidate would use the UDP transport protocol.

Example
-------

This code snippet examines the value of `protocol` to decide if it should look at the value of [`tcpType`](tcptype) to see if it's a **simultaneous-open** (**S-O**) candidate.

    if (candidate.protocol == "tcp") {
      if (candidate.tcpType == "so") {
        adjustForSimultaneousOpen(candidate);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcicecandidate-protocol">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceCandidate.protocol' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`protocol`

74

79

No

No

62

14.1

74

74

No

53

14.5

11.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/protocol" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/protocol</a>
