# RTCErrorEvent.error

The read-only [`RTCErrorEvent`](../rtcerrorevent) property `error` contains an [`RTCError`](../rtcerror) object describing the details of the error which the event is announcing.

## Syntax

    let errorInfo = rtcErrorEvent.error;

### Value

An [`RTCError`](../rtcerror) object whose properties provide details about the error which has occurred in the context of a [WebRTC](https://developer.mozilla.org/en-US/docs/Glossary/WebRTC) operation. Since `RTCError` is based upon [`DOMException`](../domexception), it includes those properties. Additional properties defined by `RTCError` are:

{{page("/en-US/docs/Web/API/RTCError", "property-list")}}

## Examples

In this example, a handler is established for an [`RTCDataChannel`](../rtcdatachannel)'s [`error`](../rtcdatachannel/error_event) event.

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

If the error is an SDP syntax error—indicated by its [`errorDetail`](../rtcerror/errordetail) property being `sdp-syntax-error`—, a message string is constructed to present the error message and the line number within the SDP at which the error occurred. This message is then displayed using a function called `showMyAlertMessage()`, which stands in for whatever output mechanism this code might use.

Any other error is treated as terminal, causing a `terminateMyConnection()` function to be called.

The above example uses [`addEventListener()`](../eventtarget/addeventlistener) to add the handler for `error` events. You can also use the `RTCDataChannel` object's [`onerror`](../rtcdatachannel/onerror) event handler property, like this:

    dataChannel.onerror = (event) => {
      let error = event.error;

      /* and so forth */
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcerrorevent-error">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCErrorEvent.error' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`error`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCErrorEvent/error" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCErrorEvent/error</a>
