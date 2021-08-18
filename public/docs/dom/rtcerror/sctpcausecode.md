# RTCError.sctpCauseCode

The read-only `sctpCauseCode` property in an [`RTCError`](../rtcerror) object provides the [SCTP](https://developer.mozilla.org/en-US/docs/Glossary/SCTP) cause code explaining why the SCTP negotiation failed, if the `RTCError` represents an SCTP error.

## Syntax

    let sctpCause = rtcError.sctpCauseCode;

### Value

An unsigned long integer value specifying SCTP cause code explaining why the error occurred. This property is `null` if the error isn't an SCTP error, with its [`errorDetail`](errordetail) property set to `sctp-failure`.

The standard SCTP error cause codes, numbered 1-13, are defined in the SCTP specification: [RFC 4960, section 3.3.10](https://tools.ietf.org/html/rfc4960#section-3.3.10).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcerror-sctpcausecode">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCError.sctpCauseCode' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`sctpCauseCode`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCError/sctpCauseCode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCError/sctpCauseCode</a>
