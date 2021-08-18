# RTCIceCandidate.RTCIceCandidate()

The ` RTCIceCandidate``() ` constructor creates and returns a new [`RTCIceCandidate`](../rtcicecandidate) object, which can be configured to represent a single [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) candidate.

## Syntax

    candidate = new RTCIceCandidate([candidateInfo]);

### Parameters

`candidateInfo` <span class="badge inline optional">Optional</span>  
An optional [`RTCIceCandidateInit`](../rtcicecandidateinit) object providing information about the candidate; if this is provided, the candidate is initialized configured to represent the described candidate.

### Return value

A newly-created [`RTCIceCandidate`](../rtcicecandidate) object, optionally configured based on the specified object based on the [`RTCIceCandidateInit`](../rtcicecandidateinit) dictionary.

If `candidateInfo` is provided, the new `RTCIceCandidate` is initialized as follows:

- Each member of the `RTCIceCandidateInit` object is initialized to the value of the property by the same name from [`RTCIceCandidateInit`](../rtcicecandidateinit). This includes the [`candidate`](candidate), [`sdpMid`](sdpmid), [`sdpMLineIndex`](sdpmlineindex), and [`usernameFragment`](usernamefragment) properties.
- The `candidate` string (which is SDP text) is parsed; each property found is stored in the corresponding field in the `RTCIceCandidate`. If any of the fields is invalid, parsing of the string silently aborts without throwing an exception. The default value of `candidate` is the empty string, which indicates that the candidate is an "end-of-candidates" message.
- The following fields are initialized to `null` if they are not included in the [`RTCIceCandidate.candidate`](candidate) property: [`foundation`](foundation), [`component`](component), [`priority`](priority) , [`ip`](address), [`protocol`](protocol), [`port`](port), [`type`](type), [`tcpType`](tcptype), [`relatedAddress`](relatedaddress), and [`relatedPort`](relatedport).

**Note:** Parsing of the `candidate` string is performed using the [candidate-attribute grammar](https://w3c.github.io/webrtc-pc/#candidate-attribute-grammar) from the WebRTC Specification.

### Exceptions

`TypeError`  
The specified `RTCIceCandidateInit` has values of `null` in both the [`sdpMid`](../rtcicecandidateinit/sdpmid) and [`sdpMLineIndex`](../rtcicecandidateinit/sdpmlineindex) properties.

## Usage notes

This constructor does not do complete validation of the specified `candidateInfo` object or string.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dfn-rtcicecandidate">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceCandidate()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

## See also

- [ICE](../webrtc_api/protocols#ice) in [Introduction to WebRTC protocols](../webrtc_api/protocols)
- [WebRTC connectivity](../webrtc_api/connectivity)
- [Lifetime of a WebRTC session](../webrtc_api/session_lifetime)
- [Signaling and video calling](../webrtc_api/signaling_and_video_calling)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/RTCIceCandidate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/RTCIceCandidate</a>
