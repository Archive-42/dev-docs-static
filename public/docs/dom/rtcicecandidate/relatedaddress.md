RTCIceCandidate.relatedAddress
==============================

The **[`RTCIceCandidate`](../rtcicecandidate)** interface's read-only `relatedAddress` property is a string indicating the **related address** of a relay or reflexive candidate. If the candidate is a host candidate (that is, its [`ip`](address) is in fact the real IP address of the remote peer), `relatedAddress` is `null`.

The `relatedAddress` field's value is set when the [`RTCIceCandidate()`](rtcicecandidate) constructor is used. You can't specify the value of `relatedAddress` in the options object, but the address is automatically extracted from the [`candidate`](../rtcicecandidateinit/candidate) a-line, if it's formatted properly, being taken from its `rel-address` field.

The related address and port ([`relatedPort`](relatedport)) are not used at all by [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) itself; they are provided for analysis and diagnostic purposes only, and their inclusion may be blocked by security systems, so do not rely on them having non-`null` values.

Syntax
------

    var relAddress = RTCIceCandidate.relatedAddress;

### Value

A [`DOMString`](../domstring) which contains the candidate's related address. For both peer and server reflexive candidates, the related address (and related port) are the base for that server or peer reflexive candidate. For relay candidates, the related address and port are set to the mapped address selected by the TURN server.

For host candidates, `relatedAddress` is `null`, meaning the field is not included in the candidate's a-line.

Usage notes
-----------

The related address is included in ICE candidates despite not being used by ICE itself. `relatedAddress` can be used for diagnostic purposes; by observing the relationships between the various types of candidates and their addresses and related addresses. `relatedAddress` can also be used by Quality-of-Service (QoS) mechanisms.

Here's an [SDP](https://developer.mozilla.org/en-US/docs/Glossary/SDP) attribute line (a-line) describing an ICE candidate discovered by the STUN server:

    a=candidate:4234997325 1 udp 2043278322 192.168.0.56 6502 typ srflx raddr 192.168.2.77 rport 32768 generation 0

The remote address, `relatedAddress`, is the dotted quad (for IPv4) or colon-delineated 64-bit address (for IPv6) immediately following the text `"raddr"`, or `"192.168.2.77"`.

Example
-------

In this example, the candidate's [`type`](type) is checked, and then debugging output is presented, based on the candidate type, including the candidate's [`ip`](address) and `relatedAddress`.

    switch(candidate.type) {
      case "host":
        console.log("Host candidate's IP address is " + candidate.ip);
        break;
      case "srflx":
        console.log("Server reflexive candidate's base address is " +
            candidate.relatedAddress + "; reachable at " + candidate.ip);
        break;
      case "prflx":
        console.log("Peer reflexive candidate's base address is " +
            candidate.relatedAddress + "; reachable at " + candidate.ip);
        break;
      case "relay":
        console.log("Relay candidate's address assigned by the TURN server is " +
            candidate.relatedAddress + "; reachable at " + candidate.ip);
        break;
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcicecandidate-relatedaddress">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceCandidate.relatedAddress' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`relatedAddress`

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

See also
--------

-   [WebRTC API](../webrtc_api)
-   [Introduction to WebRTC protocols](../webrtc_api/protocols)
-   [WebRTC connectivity](../webrtc_api/connectivity)
-   [Lifetime of a WebRTC session](../webrtc_api/session_lifetime)
-   <span class="page-not-created">`RTCIceCanddiate.relatedPort`</span>
-   [`RTCIceCandidate.address`](address) and [`RTCIceCandidate.port`](port)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/relatedAddress" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/relatedAddress</a>
