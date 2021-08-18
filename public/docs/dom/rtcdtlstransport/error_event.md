RTCDtlsTransport: error event
=============================

An [`RTCDtlsTransport`](../rtcdtlstransport) receives an `error` event when a transport-level error occurs on the [`RTCPeerConnection`](../rtcpeerconnection).

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../rtcerrorevent"><code>RTCErrorEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><span class="page-not-created"><code>onerror</code></span></td></tr></tbody></table>

The [`RTCErrorEvent`](../rtcerrorevent) object provides details about the error that occurred; see that article for details.

Description
-----------

Transport-level errors will have one of the following values for the specified error's [`RTCError`](../rtcerror) property [`errorDetail`](../rtcerror/errordetail):

`dtls-failure`  
The negotiation of the [DTLS](https://developer.mozilla.org/en-US/docs/Glossary/DTLS) connection failed, or the connection was terminated with a fatal error. The error's <span class="page-not-created">`message`</span> contains details about the nature of the error. If a fatal error is *received*, the error object's [`receivedAlert`](../rtcerror/receivedalert) property is set to the value of the DTLSL alert received. If, on the other hand, a fatal error was *sent*, the [`sentAlert`](../rtcerror/sentalert) is set to the alert's value.

`fingerprint-failure`  
The remote certificate for the [`RTCDtlsTransport`](../rtcdtlstransport) didn't match any of the fingerprints listed in the SDP. If the remote peer can't match the local certificate against the provided fingerprints, this error doesn't occur, though this situation may result instead in a `dtls-failure` error.

Examples
--------

In this example, the <span class="page-not-created">`onerror`</span> event handler property is used to set the handler for the `error` event.

    transport.onerror = ev => {
      const err = ev.error;

      /* ... */
    }

**Note:** Since `RTCError` is not one of the legacy errors, the value of [`RTCError.code`](../domexception/code) is always 0.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dfn-rtcdtlstransport-error">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCDtlsTransport: error event' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.RTCDtlsTransport.error_event`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

-   [WebRTC API](../webrtc_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDtlsTransport/error_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCDtlsTransport/error_event</a>
