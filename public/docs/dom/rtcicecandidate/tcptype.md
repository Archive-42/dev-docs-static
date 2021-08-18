# RTCIceCandidate.tcpType

The **[`RTCIceCandidate`](../rtcicecandidate)** interface's read-only `tcpType` property is included on TCP candidates to provide additional details about the candidate type.

The `tcpType` field's value is set when the [`RTCIceCandidate()`](rtcicecandidate) constructor is used. You can't directly set its value; instead, its value is automatically extracted from the [`candidate`](../rtcicecandidateinit/candidate) a-line, if it's formatted properly.

## Syntax

    var tcpType = RTCIceCandidate.tcpType;

### Value

A [`DOMString`](../domstring) whose value is one of those defined by the [`RTCIceTcpCandidateType`](../rtcicetcpcandidatetype) enumerated type.

`"active"`  
The transport will try to open an outbound connection but won't receive inoming connection requests.

`"passive"`  
The transport will receive incoming connection requests but won't try to open an outbound connection.

`"so"`  
The transport will try to open a connection simultaneously with its peer.

`tcpType` is `null` for [UDP](https://developer.mozilla.org/en-US/docs/Glossary/UDP) candidates.

## Example

In this example, the candidate's [`protocol`](protocol) and `tcpType` are used to adjust the user interface for simultaneous-open TCP candidates.

    if (candidate.protocol == "tcp" && candidate.tcpType == "so") {
        adjustForSimultaneousOpen(candidate);
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcicecandidate-tcptype">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceCandidate.tcpType' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

## See also

- [WebRTC API](../webrtc_api)
- [Introduction to WebRTC protocols](../webrtc_api/protocols)
- [WebRTC connectivity](../webrtc_api/connectivity)
- [`RTCIceCandidate.protocol`](protocol)
- [`RTCIceCandidate.type`](type)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/tcpType" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/tcpType</a>
