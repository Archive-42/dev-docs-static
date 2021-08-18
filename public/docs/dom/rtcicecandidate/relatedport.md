RTCIceCandidate.relatedPort
===========================

The **[`RTCIceCandidate`](../rtcicecandidate)** interface's read-only `relatedPort` property indicates the port number of reflexive or relay candidates. If the candidate is a host candidate (that is, its [`ip`](address) is in fact the real IP address of the remote peer), `relatedPort` is `null`.

The `relatedPort` field's value is set when the [`RTCIceCandidate()`](rtcicecandidate) constructor is used. You can't specify the value of `relatedPort` in the options object, but the address is automatically extracted from the [`candidate`](../rtcicecandidateinit/candidate) a-line, if it's formatted properly, being taken from its `rel-port` field.

The related address ([`relatedAddress`](relatedaddress)) and port are not used at all by [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) itself; they are provided for analysis and diagnostic purposes only, and their inclusion may be blocked by security systems, so do not rely on them having non-`null` values.

Syntax
------

    var relPort = RTCIceCandidate.relatedPort;

### Value

An unsigned 16-bit value containing the candidate's related port number, if any. For both peer and server reflexive candidates, the related address and port describe the base for that candidate. For relay candidates, the related address and port provide the mapped address selected by the TURN server.

For host candidates, `relatedPort` is `null`, meaning the field is not included in the candidate's a-line.

Usage notes
-----------

The related address and port are not used by ICE itself, and are only present for diagnostic and Quality-of-Service purposes. They may in fact be omitted for security reasons, but if present can be a useful tool during debugging. See the [example](#example), which shows a bit of this.

Here's an [SDP](https://developer.mozilla.org/en-US/docs/Glossary/SDP) attribute line (a-line) describing an ICE candidate discovered by the STUN server:

    a=candidate:4234997325 1 udp 2043278322 192.168.0.56 6502 typ srflx raddr 192.168.2.77 rport 32768 generation 0

The remote port, `relatedPort`, is the number immediately following the `"rport"` label on the a-line, or 32768.

Example
-------

In this example, the candidate's [`type`](type) is checked, and then debugging output is presented, based on the candidate type, including the candidate's type, address (`ip` and [`port`](port)), and related address ([`relatedAddress`](relatedaddress) and `relatedPort`).

    var ip = candidate.ip;
    var port = candidate.port;
    var relIP = candidate.relatedAddress;
    var relPort = candidate.relatedPort;

    if (relIP && relPort) {
      console.log("Candidate type '" + type + "' -- contact address: " + ip + " " + port + ", related address: " + relIP + " " + relPort);
    } else {
      console.log("Host candidate address is " + ip + " " + port);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcicecandidate-relatedport">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceCandidate.relatedPort' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`relatedPort`

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
-   <span class="page-not-created">`RTCIceCanddiate.relatedAddress`</span>
-   [`RTCIceCandidate.address`](address) and [`RTCIceCandidate.port`](port)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/relatedPort" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/relatedPort</a>
