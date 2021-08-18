# RTCIceCandidate.component

The read-only `component` property on the [`RTCIceCandidate`](../rtcicecandidate) interface is a string which indicates whether the candidate is an [RTP](../webrtc_api/intro_to_rtp) or an RTCP candidate.

If a candidate represents both RTP and RTCP multiplexed together, it is reported as an RTP candidate.

## Syntax

    var component = RTCIceCandidate.component;

### Value

A [`DOMString`](../domstring) which is `"rtp"` for RTP (or RTP and RTCP multiplexed together) candidates or `"rtcp"` for RTCP candidates.

## Usage notes

Consider this [SDP](https://developer.mozilla.org/en-US/docs/Glossary/SDP) attribute line (a-line):

    a=candidate:4234997325 1 udp 2043278322 192.168.0.56 44323 typ host

This is an ICE candidate a-line, whose [`foundation`](foundation) is 4234997325. The next field on the a-line, `"1"`, is the component ID. A value of `"1"` indicates RTP, which is recorded in the `component` property as `"rtp"`. If this value were instead `"2"`, the a-line would be describing an RTCP candidate, and `compoment` would be `"rtcp"`.

## Example

This code snippet examines a candidate's component type and dispatches the candidate to different handlers depending on the value.

    if (candidate.component == "rtp") {
      handleRTPCandidate(candidate);
    } else if (candidate.component == "rtcp") {
      handleRTCPCandidate(candidate);
    } else {
      handleUnknownCandidate(candidate);
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcicecandidate-component">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceCandidate.component' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/component" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/component</a>
