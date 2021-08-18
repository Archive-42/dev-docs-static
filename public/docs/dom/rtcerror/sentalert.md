# RTCError.sentAlert

The read-only `sentAlert` property in an [`RTCError`](../rtcerror) object specifies the [DTLS](https://developer.mozilla.org/en-US/docs/Glossary/DTLS) alert number occurred while sending data to the remote peer, if the error represents an outbound DTLS error.

## Syntax

    let sentAlert = rtcError.sentAlert;

### Value

An unsigned integer value providing the DTLS alert number corresponding to the DTLS error which was sent to the remote peer, as represented by this `RTCError` object. This property is `null` if [`errorDetail`](errordetail) isn't `dtls-failure`.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcerror-sentalert">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCError.sentAlert' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`sentAlert`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCError/sentAlert" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCError/sentAlert</a>
