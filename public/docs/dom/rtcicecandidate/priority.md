# RTCIceCandidate.priority

The **[`RTCIceCandidate`](../rtcicecandidate)** interface's read-only `priority` property specifies the candidate's priority according to the remote peer; the higher this value is, the better the remote peer considers the candidate to be.

As is the case with most of `RTCIceCandidate`'s properties, the value of `priority` is extracted from the `candidate` a-line string specified when creating the `RTCIceCandidate`. The a-line string is obtained either from the [`RTCIceCandidateInit`](../rtcicecandidateinit) property [`candidate`](../rtcicecandidateinit/candidate) or from an a-line string passed into [`RTCPeerConnection.addIceCandidate()`](../rtcpeerconnection/addicecandidate) instead of an `RTCIceCandidate`.

## Syntax

    var priority = RTCIceCandidate.priority;

### Value

A long, unsigned integer value indicating the priority of the candidate according to the remote peer. The larger this value is, the more preferable the remote peer considers this candidate to be.

`priority` is initialized to `null` if it is not specified in the `candidate`, or if the `candidate` string can't be parsed properly.

**Note:** If `priority` is `null`, passing the candidate to [`addIceCandidate()`](../rtcpeerconnection/addicecandidate) will fail, throwing an `OperationError` exception. This applies only if the candidate implements the `priority` property.

## Usage notes

Consider this [SDP](https://developer.mozilla.org/en-US/docs/Glossary/SDP) attribute line (a-line) which describes an ICE candidate:

    a=candidate:4234997325 1 udp 2043278322 192.168.0.56 44323 typ host

The priority is the number after the protocol, so it's the fourth field in the candidate string. In this example, the priority is 2043278322.

## Example

This candidate examines the `priority` of the candidate and, if it's greater than the priority of a previously-seen candidate, remembers the candidate for later use.

    var bestCandidate = {
      candidate: "",
      sdpMid: null,
      sdpMLineIndex: null,
      priority: 0
    };

    function handleCandidate(candidateString) {
      var candidate = new RTCIceCandidate(candidateString);

      if (candidate.priority > bestCandidate.priority) {
        bestCandidate = candidate;
      }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcicecandidate-priority">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceCandidate.priority' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/priority" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/priority</a>
