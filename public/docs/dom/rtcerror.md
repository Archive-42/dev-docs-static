RTCError
========

The `RTCError` interface describes an error which has occurred while handling [WebRTC](webrtc_api) operations. It's based upon the standard [`DOMException`](domexception) interface that describes general DOM errors.

Constructor
-----------

<span class="page-not-created">`RTCError()`</span>  
Creates and returns a new `RTCError` object initialized with the properties of the provided <span class="page-not-created">`RTCErrorInit`</span> dictionary and, optionally, a string to use as the value of the error's [`message`](domexception/message) property.

Properties
----------

*In addition to the properties defined by the parent interface, [`DOMException`](domexception), `RTCError` includes the following properties:*

 [`errorDetail`](rtcerror/errordetail) <span class="badge inline readonly">Read only </span>   
A [`DOMString`](domstring) specifying the WebRTC-specific error code identifying the type of error that occurred.

 [`receivedAlert`](rtcerror/receivedalert) <span class="badge inline readonly">Read only </span>   
An unsigned long integer value indicating the fatal [DTLS](https://developer.mozilla.org/en-US/docs/Glossary/DTLS) error which was received from the network. Only valid if the `errorDetail` string is `dtls-failure`. If `null`, no DTLS error was received.

 [`sctpCauseCode`](rtcerror/sctpcausecode) <span class="badge inline readonly">Read only </span>   
If `errorDetail` is `sctp-failure`, this property is a long integer specifying the [SCTP](https://developer.mozilla.org/en-US/docs/Glossary/SCTP) cause code indicating the cause of the failed SCTP negotiation. `null` if the error isn't an SCTP error.

 [`sdpLineNumber`](rtcerror/sdplinenumber) <span class="badge inline readonly">Read only </span>   
If `errorDetail` is `sdp-syntax-error`, this property is a long integer identifying the line number of the [SDP](https://developer.mozilla.org/en-US/docs/Glossary/SDP) on which the syntax error occurred. `null` if the error isn't an SDP syntax error.

 [`sentAlert`](rtcerror/sentalert) <span class="badge inline readonly">Read only </span>   
If `errorDetail` is `dtls-failure`, this property is an unsigned long integer indicating the fatal DTLS error that was sent out by this device. If `null`, no DTLS error was transmitted.

All `RTCError` objects have their [`name`](domexception/name) set to `OperationError`.

Examples
--------

In this example, a handler is established for an [`RTCDataChannel`](rtcdatachannel)'s [`error`](rtcdatachannel/error_event) event.

    dataChannel.addEventListener("error", (event) => {
      let error = event.error;

      if (error.errorDetail === "sdp-syntax-error") {
        let errLine = error.sdpLineNumber;
        let errMessage = error.message;

        let alertMessage = `A syntax error occurred interpreting line ${errLine} of the SDP: ${errMessage}`;
        showMyAlertMessage("Data Channel Error", alertMessage);
      } else {
        terminateMyConnection();
      }
    });

If the error is an SDP syntax error—indicated by its [`errorDetail`](rtcerror/errordetail) property being `sdp-syntax-error`—, a message string is constructed to present the error message and the line number within the SDP at which the error occurred. This message is then displayed using a function called `showMyAlertMessage()`, which stands in for whatever output mechanism this code might use.

Any other error is treated as terminal, causing a `terminateMyConnection()` function to be called.

The above example uses [`addEventListener()`](eventtarget/addeventlistener) to add the handler for `error` events. You can also use the `RTCDataChannel` object's [`onerror`](rtcdatachannel/onerror) event handler property, like this:

    dataChannel.onerror = (event) => {
      let error = event.error;

      /* and so forth */
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcerror">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCError' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`RTCError`

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

`RTCError`

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

`httpRequestStatusCode`

74

79

No

No

62

No

74

74

No

53

No

11.0

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCError" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCError</a>
