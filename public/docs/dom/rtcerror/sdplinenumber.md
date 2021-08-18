# RTCError.sdpLineNumber

The [`RTCError`](../rtcerror) interface's read-only property `sdpLineNumber` specifies the line number within the [SDP](https://developer.mozilla.org/en-US/docs/Glossary/SDP) at which a syntax error occurred while parsing it.

## Syntax

    let errorLineNumber = rtcError.sdpLineNumber;

### Value

An unsigned integer value indicating the line within the SDP at which the syntax error described by the `RTCError` object occurred. The lines are numbed starting with line 1.

This property is `null` unless the value of [`errorDetail`](errordetail) is `sdp-syntax-error`.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcerror-sdplinenumber">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCError.sdpLineNumber' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`sdpLineNumber`

74

79

No

No

60

No

74

74

No

53

No

11.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCError/sdpLineNumber" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCError/sdpLineNumber</a>
