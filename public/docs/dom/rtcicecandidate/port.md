# RTCIceCandidate.port

The **[`RTCIceCandidate`](../rtcicecandidate)** interface's read-only `port` property contains the port number on the device at the address given by [`ip`](address) at which the candidate's peer can be reached.

As is the case with most of `RTCIceCandidate`'s properties, the value of `port` is extracted from the `candidate` a-line string specified when creating the `RTCIceCandidate`. The a-line string is obtained either from the [`RTCIceCandidateInit`](../rtcicecandidateinit) property [`candidate`](../rtcicecandidateinit/candidate) or from a-line string passed into the constructor upon using [`new RTCIceCandidate()`](rtcicecandidate).

## Syntax

    var port = RTCIceCandidate.port;

### Value

A 16-bit number indicating the port number on the device at the address indicated by [`ip`](address) at which the candidate's peer can be reached.

`port` is initialized to `null` if it is not specified in the `candidate`, or if the `candidate` string can't be parsed properly.

**Note:** If `port` is `null`, passing the candidate to [`addIceCandidate()`](../rtcpeerconnection/addicecandidate) will fail, throwing an `OperationError` exception. This applies only if the candidate implements `port`.

## Usage notes

Consider this [SDP](https://developer.mozilla.org/en-US/docs/Glossary/SDP) attribute line (a-line) which describes an ICE candidate:

    a=candidate:4234997325 1 udp 2043278322 192.168.0.56 44323 typ host

The port number is found in the sixth field, which is `"44323"`. In this case, the value of `port` will be 44323.

## Example

This code snippet fetches the IP address and port number of the candidate, storing them into an object for future use.

    var candidateLoc = {
      address: candidate.ip,
      port: candidate.port
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcicecandidate-port">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceCandidate.port' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/port" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/port</a>
