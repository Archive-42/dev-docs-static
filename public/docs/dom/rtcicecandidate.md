# RTCIceCandidate

The `RTCIceCandidate` interface—part of the [WebRTC API](webrtc_api)—represents a candidate Internet Connectivity Establishment ([ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE)) configuration which may be used to establish an [`RTCPeerConnection`](rtcpeerconnection).

An ICE candidate describes the protocols and routing needed for WebRTC to be able to communicate with a remote device. When starting a WebRTC peer connection, typically a number of candidates are proposed by each end of the connection, until they mutually agree upon one which describes the connection they decide will be best. WebRTC then uses that candidate's details to initiate the connection.

For details on how the ICE process works, see [Lifetime of a WebRTC session](webrtc_api/session_lifetime). The article [WebRTC connectivity](webrtc_api/connectivity) provides additional useful details.

## Constructor

[`RTCIceCandidate()`](rtcicecandidate/rtcicecandidate)  
Creates an `RTCIceCandidate` object to represent a single ICE candidate, optionally configured based on an object based on the [`RTCIceCandidateInit`](rtcicecandidateinit) dictionary.

**Note:** For backward compatibility, the constructor also accepts as input a string containing the value of the [`candidate`](rtcicecandidate/candidate) property instead of a [`RTCIceCandidateInit`](rtcicecandidateinit) object, since the `candidate` includes all of the information that `RTCIceCandidateInit` does and more.

## Properties

[`candidate`](rtcicecandidate/candidate) <span class="badge inline readonly">Read only </span>  
A [`DOMString`](domstring) representing the transport address for the candidate that can be used for connectivity checks. The format of this address is a `candidate-attribute` as defined in [RFC 5245](https://tools.ietf.org/html/rfc5245). This string is empty (`""`) if the `RTCIceCandidate` is an "end of candidates" indicator.

[`component`](rtcicecandidate/component) <span class="badge inline readonly">Read only </span>  
A [`DOMString`](domstring) which indicates whether the candidate is an RTP or an RTCP candidate; its value is either `"rtp"` or `"rtcp"`, and is derived from the `"component-id"` field in the `candidate` a-line string. The permitted values are listed in the [`RTCIceComponent`](rtcicecomponent) enumerated type.

[`foundation`](rtcicecandidate/foundation) <span class="badge inline readonly">Read only </span>  
Returns a [`DOMString`](domstring) containing a unique identifier that is the same for any candidates of the same type, share the same base (the address from which the ICE agent sent the candidate), and come from the same [STUN](https://developer.mozilla.org/en-US/docs/Glossary/STUN) server. This is used to help optimize ICE performance while prioritizing and correlating candidates that appear on multiple [`RTCIceTransport`](rtcicetransport) objects.

[`ip`](rtcicecandidate/address) <span class="badge inline readonly">Read only </span>  
A [`DOMString`](domstring) containing the IP address of the candidate.

[`port`](rtcicecandidate/port) <span class="badge inline readonly">Read only </span>  
An integer value indicating the candidate's port number.

[`priority`](rtcicecandidate/priority) <span class="badge inline readonly">Read only </span>  
A long integer value indicating the candidate's priority.

[`address`](rtcicecandidate/address) <span class="badge inline readonly">Read only </span>  
The address of the candidate.

[`protocol`](rtcicecandidate/protocol) <span class="badge inline readonly">Read only </span>  
A string indicating whether the candidate's protocol is `"tcp"` or `"udp"`. The string is one of those in the enumerated type `RTCIceProtocol`.

[`relatedAddress`](rtcicecandidate/relatedaddress) <span class="badge inline readonly">Read only </span>  
If the candidate is derived from another candidate, `relatedAddress` is a [`DOMString`](domstring) containing that host candidate's IP address. For host candidates, this value is `null`.

[`relatedPort`](rtcicecandidate/relatedport) <span class="badge inline readonly">Read only </span>  
For a candidate that is derived from another, such as a relay or reflexive candidate, the `relatedPort` is a number indicating the port number of the candidate from which this candidate is derived. For host candidates, the `relatedPort` property is `null`.

[`sdpMid`](rtcicecandidate/sdpmid) <span class="badge inline readonly">Read only </span>  
A [`DOMString`](domstring) specifying the candidate's media stream identification tag which uniquely identifies the media stream within the component with which the candidate is associated, or `null` if no such association exists.

[`sdpMLineIndex`](rtcicecandidate/sdpmlineindex) <span class="badge inline readonly">Read only </span>  
If not `null`, `sdpMLineIndex` indicates the zero-based index number of the media description (as defined in [RFC 4566](https://datatracker.ietf.org/doc/html/rfc4566)) in the [SDP](https://developer.mozilla.org/en-US/docs/Glossary/SDP) with which the candidate is associated.

[`tcpType`](rtcicecandidate/tcptype) <span class="badge inline readonly">Read only </span>  
If `protocol` is `"tcp"`, `tcpType` represents the type of TCP candidate. Otherwise, `tcpType` is `null`.

[`type`](rtcicecandidate/type) <span class="badge inline readonly">Read only </span>  
A [`DOMString`](domstring) indicating the type of candidate as one of the strings from the [`RTCIceCandidateType`](rtcicecandidatetype) enumerated type.

[`usernameFragment`](rtcicecandidate/usernamefragment) <span class="badge inline readonly">Read only </span>  
A [`DOMString`](domstring) containing a randomly-generated username fragment ("ice-ufrag") which ICE uses for message integrity along with a randomly-generated password ("ice-pwd"). You can use this string to verify generations of ICE generation; each generation of the same ICE process will use the same `usernameFragment`, even across ICE restarts.

## Methods

[`toJSON()`](rtcicecandidate/tojson)  
Given the `RTCIceCandidate`'s current configuration, `toJSON()` returns a [`DOMString`](domstring) containing a [JSON](https://developer.mozilla.org/en-US/docs/Glossary/JSON) representation of that configuration in the form of a [`RTCIceCandidateInit`](rtcicecandidateinit) object.

## Examples

For examples, see the article [Signaling and video calling](webrtc_api/signaling_and_video_calling), which demonstrates the entire process.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#rtcicecandidate-interface">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceCandidate' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

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

`RTCIceCandidate`

23

15

22

No

15

11

≤37

25

Yes

14

11

1.5

`RTCIceCandidate`

23

15

22

Before Firefox 68, the constructor's `options` parameter was required.

No

15

11

≤37

25

Yes

Before Firefox 68, the constructor's `options` parameter was required.

14

11

1.5

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

`candidate`

23

15

22

No

15

11

≤37

25

Yes

14

11

1.5

`component`

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

`foundation`

74

79

No

No

62

14.1

74

74

?

53

14.5

11.0

`port`

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

`priority`

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

`sdpMid`

23

15

22

No

15

11

≤37

25

Yes

14

11

1.5

`sdpMLineIndex`

23

15

22

No

15

11

≤37

25

Yes

14

11

1.5

`tcpType`

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

`toJSON`

45

15

27

No

32

11

45

45

27

32

11

5.0

`type`

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

`usernameFragment`

74

79

67

No

62

14.1

74

74

67

53

14.5

11.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate</a>
