RTCError.errorDetail
====================

The [`RTCError`](../rtcerror) interface's read-only `errorDetail` property is a string indicating the [WebRTC](../webrtc_api)-specific error code that occurred.

Syntax
------

    let rtcErrorDetail = rtcError.errorDetail;

### Value

A read-only string whose value indicates the type of WebRTC-specific error that occurred on an [`RTCPeerConnection`](../rtcpeerconnection). The possible values are taken from the `RTCErrorDetailType` enumeration:

`data-channel-failure`  
The connection's [`RTCDataChannel`](../rtcdatachannel) has failed.

`dtls-failure`  
The negotiation of the [DTLS](https://developer.mozilla.org/en-US/docs/Glossary/DTLS) connection failed, or the connection was terminated with a fatal error. The error's <span class="page-not-created">`message`</span> contains details about the nature of the error. If a fatal error is *received*, the error object's [`receivedAlert`](receivedalert) property is set to the value of the DTLSL alert received. If, on the other hand, a fatal error was *sent*, the [`sentAlert`](sentalert) is set to the alert's value.

`fingerprint-failure`  
The remote certificate for the [`RTCDtlsTransport`](../rtcdtlstransport) didn't match any of the fingerprints listed in the SDP. If the remote peer can't match the local certificate against the provided fingerprints, this error doesn't occur, though this situation may result instead in a `dtls-failure` error.

`hardware-encoder-error`  
The hardsare encoder doesn't support the given configuration parameters.

`hardware-encoder-not-available`  
The hardware encoder resources required to accomplish the requested operation aren't available.

`sctp-failure`  
The [SCTP](https://developer.mozilla.org/en-US/docs/Glossary/SCTP) negotiation has failed, or the connection has terminated with a fatal error. The SCTP cause code can be found in the `RTCError` object's [`sctpCauseCode`](sctpcausecode). SCTP error cause codes 1-13 are defined in the SCTP specification: [RFC 4960, section 3.3.10](https://tools.ietf.org/html/rfc4960#section-3.3.10).

`sdp-syntax-error`  
The SDP syntax is invalid. The error's [`sdpLineNumber`](sdplinenumber) property indicates the line number within the SDP at which the error was detected.

Examples
--------

tbd

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcerror-errordetail">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCError.errorDetail' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`errorDetail`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCError/errorDetail" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCError/errorDetail</a>
