RTCError.receivedAlert
======================

The [`RTCError`](../rtcerror) read-only property `receivedAlert` specifies the fatal [DTLS](https://developer.mozilla.org/en-US/docs/Glossary/DTLS) error which resulted in an alert being received from the remote peer.

Syntax
------

    let receivedAlert = rtcError.receivedAlert;

### Value

An unsigned long integer value specifying the fatal [DTLS](https://developer.mozilla.org/en-US/docs/Glossary/DTLS) error which resulted in an alert being received from the remote peer.

This property is `null` if the `RTCError` doesn't represent a DTLS error (with [`errorDetail`](errordetail) set to `dtls-failure`).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcerror-receivedalert">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCError.receivedAlert' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`receivedAlert`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCError/receivedAlert" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCError/receivedAlert</a>
