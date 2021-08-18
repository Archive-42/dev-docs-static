RTCIceCandidateStats
====================

The WebRTC API's `RTCIceCandidateStats` dictionary provides statistics related to an [`RTCIceCandidate`](rtcicecandidate).

Properties
----------

`RTCIceCandidateStats` is based upon the [`RTCStats`](rtcstats) dictionary, so it includes those properties in addition to the ones below.

 [`address`](rtcicecandidatestats/address) <span class="badge inline optional">Optional</span>   
A string containing the address of the candidate. This value may be an IPv4 address, an IPv6 address, or a fully-qualified domain name. This property was previously named `ip` and only accepted IP addresses.

 [`candidateType`](rtcicecandidatestats/candidatetype) <span class="badge inline optional">Optional</span>   
A string matching one of the values in the [`RTCIceCandidateType`](rtcicecandidatetype) enumerated type, indicating what kind of candidate the object provides statistics for.

 [`deleted`](rtcicecandidatestats/deleted) <span class="badge inline optional">Optional</span>   
A Boolean value indicating whether or not the candidate has been released or deleted; the default value is `false`. For local candidates, it's value is `true` if the candidate has been deleted or released. For host candidates, `true` means that any network resources (usually a network socket) associated with the candidate have already been released. For [TURN](https://developer.mozilla.org/en-US/docs/Glossary/TURN) candidates, the TURN allocation is no longer active for deleted candidates. This property is not present for remote candidates.

 [`networkType`](rtcicecandidatestats/networktype) <span class="badge inline optional">Optional</span>   
A string from the [`RTCNetworkType`](rtcnetworktype) enumerated type which indicates the type of interface used for a local candidate. This property is only present for local candidates.

 [`port`](rtcicecandidatestats/port) <span class="badge inline optional">Optional</span>   
The network port number used by the candidate.

 [`priority`](rtcicecandidatestats/priority) <span class="badge inline optional">Optional</span>   
The candidate's priority, corresponding to [`RTCIceCandidate.priority`](rtcicecandidate/priority).

 [`protocol`](rtcicecandidatestats/protocol) <span class="badge inline optional">Optional</span>   
A string specifying the protocol (`tcp` or `udp`) used to transmit data on the `port`.

 [`relayProtocol`](rtcicecandidatestats/relayprotocol) <span class="badge inline optional">Optional</span>   
A string identifying the protocol used by the endpoint for communicating with the [TURN](https://developer.mozilla.org/en-US/docs/Glossary/TURN) server; valid values are `tcp`, `udp`, and `tls`. Only present for local candidates.

 [`transportId`](rtcicecandidatestats/transportid) <span class="badge inline optional">Optional</span>   
A string uniquely identifiying the transport object that was inspected in order to obtain the <span class="page-not-created">`RTCTransportStats`</span> associated with the candidate correspondin to these statistics.

 [`url`](rtcicecandidatestats/url) <span class="badge inline optional">Optional</span>   
For local candidates, the `url` property is the [URL](https://developer.mozilla.org/en-US/docs/Glossary/URL) of the [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) server from which the candidate was received. This URL matches the one included in the [`RTCPeerConnectionIceEvent`](rtcpeerconnectioniceevent) object representing the `icecandidate` event that delivered the candidate to the local peer.

Example
-------

This example features a function, `isUsableNetworkType()`, whose job it is to look at an `RTCIceCandidateStats` object's [`networkType`](rtcicecandidatestats/networktype) and determine whether or not the type of network is acceptable for use.

This function is then called for [`RTCStats`](rtcstats) objects whose type is `local-candidate`, indicating that the object is in fact an `RTCIceCandidateStats` with information about a local ICE candidate.

    const isUsableNetworkType = stats => {
      switch(stats.networkType) {
        case "ethernet":
        case "vpn":
          return true;

        case "bluetooth":
        case "cellular":
        case "wimax":
        case "unknown":
        default:
          return false;
      }
    }

    if (rtcStats && rtcStats.type === "local-candidate") {
      if (!isUsableNetworkType(rtcStats)) {
        abortConnection();
        return;
      }
    }

This code calls a function called `abortConnection()` if the `RTCStats` object represents information about a local candidate is which would be using a network connection other than Ethernet or a VPN.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#icecandidate-dict*">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCIceCandidateStats' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`RTCIceCandidateStats`

No

No

27

No

?

?

No

No

27

?

?

No

`address`

No

No

65

27

No

?

?

No

No

65

27

?

?

No

`candidateType`

No

No

27

No

?

?

No

No

27

?

?

No

`componentId`

No

No

29

`componentId` is a Firefox-specific property and should not be used in production code.

No

?

?

No

No

29

`componentId` is a Firefox-specific property and should not be used in production code.

?

?

No

`deleted`

No

No

No

No

?

?

No

No

No

?

?

No

`networkType`

No

No

No

No

?

?

No

No

No

?

?

No

`port`

No

No

27

No

?

?

No

No

27

?

?

No

`priority`

No

No

No

No

?

?

No

No

No

?

?

No

`protocol`

No

No

64

31

No

?

?

No

No

64

31

?

?

No

`relayProtocol`

No

No

64

31

No

?

?

No

No

64

31

?

?

No

`transportId`

No

No

31

No

?

?

No

No

31

?

?

No

`url`

No

No

No

No

?

?

No

No

No

?

?

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidateStats" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidateStats</a>
