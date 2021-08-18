RTCDataChannel: error event
===========================

A WebRTC [`error`](error_event) event is sent to an [`RTCDataChannel`](../rtcdatachannel) object's [`onerror`](onerror) error handler when an error occurs on the data channel.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../rtcerrorevent"><code>RTCErrorEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onerror"><code>onerror</code></a></td></tr></tbody></table>

The [`RTCErrorEvent`](../rtcerrorevent) object provides details about the error that occurred; see that article for details.

Examples
--------

    // Strings for each of the SCTP cause codes found in RFC
    // 4960, section 3.3.10:
    // https://datatracker.ietf.org/doc/html/rfc4960#section-3.3.10

    const sctpCauseCodes = [
      "No SCTP error",
      "Invalid stream identifier",
      "Missing mandatory parameter",
      "Stale cookie error",
      "Sender is out of resource (i.e., memory)",
      "Unable to resolve address",
      "Unrecognized SCTP chunk type received",
      "Invalid mandatory parameter",
      "Unrecognized parameters",
      "No user data (SCTP DATA chunk has no data)",
      "Cookie received while shutting down",
      "Restart of an association with new addresses",
      "User-initiated abort",
      "Protocol violation"
    ];

    dc.addEventListener("error", ev => {
      const err = ev.error;

      console.error("WebRTC error: ", err.message);

      // Handle specific error detail types

      switch(err.errorDetail) {
        case "sdp-syntax-error":
          console.error("    SDP syntax error in line ", err.sdpLineNumber);
          break;
        case "idp-load-failure":
          console.error("    Identity provider load failure: HTTP error ",
                        err.httpRequestStatusCode);
          break;
        case "sctp-failure":
          if (err.sctpCauseCode < sctpCauseCodes.length) {
            console.error("    SCTP failure: ", err.sctpCauseCode);
          } else {
            console.error("    Unknown SCTP error");
          }
          break;
        case "dtls-failure":
          if (err.receivedAlert) {
            console.error("    Received DLTS failure alert: ", err.receivedAlert);
          }
          if (err.sentAlert) {
            console.error("    Sent DLTS failure alert: ", err.receivedAlert);
          }
          break;
      }

      // Add source file name and line information

      console.error("    Error in file ", err.filename, " at line ", err.lineNumber,
                    ", column ", err.columnNumber);
    }, false);

The received event provides details in an [`RTCError`](../rtcerror) object called [`error`](../rtcerrorevent/error); `RTCError` is an extension of the [`DOMException`](../domexception) interface. The error's [`name`](../domexception/name) is `RTCError` and the [`message`](../domexception/message) is an error string specified by the WebRTC layer.

Error information is output to the console using [`console.error()`](../console/error). The `message` string is always output, as is information about the source file's name, line number, and column number at which the error occurred.

In addition, however, depending on the value of [`errorDetail`](../rtcerror/errordetail), additional information may be output. Each error type has a different set of information output. For example, an SDP syntax error displays the line number of the error within the SDP, and an SCTP error displays a message corresponding to the SCTP cause code. Other error types similarly output appropriate information.

You can also set up an event handler for `error` events using the `RTCDataChannel` interface's [`onerror`](onerror) event handler property:

    dc.onerror = ev => {
      const err = ev.error;

      /* ... */
    }

**Note:** Since `RTCError` is not one of the legacy errors, the value of [`RTCError.code`](../domexception/code) is always 0.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#event-datachannel-error">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'error event' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`error_event`

56

≤79

Yes

No

43

?

56

56

Yes

43

No

6.0

See also
--------

-   [WebRTC API](../webrtc_api)
-   [A simple RTCDataChannel example](../webrtc_api/simple_rtcdatachannel_sample)
-   Related events: [`open`](open_event), [`message`](message_event), and [`close`](close_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/error_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/error_event</a>
