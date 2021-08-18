RTCIceCandidate.address
=======================

The **[`RTCIceCandidate`](../rtcicecandidate)** interface's read-only `address` property is a string providing the address of the device which is the source of the candidate. `address` is `null` by default if not otherwise specified.

The `address` field's value is set when the [`RTCIceCandidate()`](rtcicecandidate) constructor is used. You can't specify the `address` in the options object, but the address is automatically extracted from the [`candidate`](../rtcicecandidateinit/candidate) a-line, if it's formatted properly.

Syntax
------

    var address = RTCIceCandidate.address;

### Value

A [`DOMString`](../domstring) providing the IP address from which the candidate comes.

**Note:** If `port` is `null` — and `port` is supported by the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) — passing the candidate to [`addIceCandidate()`](../rtcpeerconnection/addicecandidate) will fail, throwing an `OperationError` exception.

Security notes
--------------

It's important to note here that although WebRTC does not require the two peers on an [`RTCPeerConnection`](../rtcpeerconnection) to know one another's true IP addresses, the `address` property on `RTCIceCandidate` *can* expose more information about the source of the remote peer than the user expects. The IP address can be used to derive information about the remote device's location, network topology, and so forth. It can also be used for fingerprinting purposes.

The candidate IP addresses are *always* exposed to the application through `address`, and unsavory applications can in turn potentially reveal the address to the user. This can occur without the remote peer's consent.

Applications being built with user privacy and security in mind can choose to limit the permitted candidates to relay candidates only. Doing so prevents the remote user's address from being exposed, but reduces the pool of available candidates to choose from. To do this, configure the ICE agent's ICE transport policy using [`RTCConfiguration`](../rtcconfiguration), like this:

    var rtcConfig = {
      iceServers: [
        {
          urls: "turn:myturn.server.ip",
          username: "username",
          credential: "password"
        }
      ],
      iceTransportPolicy: "relay"
    }

By setting [`RTCConfiguration.iceTransportPolicy`](../rtcconfiguration/icetransportpolicy) to `"relay"`, any host candidates (candidates where the IP address is the peer's own IP address) are left out of the pool of candidates, as are any other candidates which aren't relay candidates.

Usage notes
-----------

Consider this [SDP](https://developer.mozilla.org/en-US/docs/Glossary/SDP) attribute line (a-line) which describes an ICE candidate:

    a=candidate:4234997325 1 udp 2043278322 192.168.0.56 44323 typ host

The fifth field, `"192.168.0.56"` is the IP address in this candidate's a-line string.

Example
-------

This code snippet uses the value of `address` to implement an IP address based ban feature.

    if (ipBanList.includes(candidate.address)) {
      rejectCandidate(candidate);
    } else {
      acceptCandidate(candidate);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcicecandidate-address">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceCandidate: address' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`address`

74

79

≤18-79

?

No

62

14.1

74

74

?

53

14.5

11.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/address" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/address</a>
