# RTCDtlsTransport.state

The `state` read-only property of the [`RTCDtlsTransport`](../rtcdtlstransport) interface provides information which describes a Datagram Transport Layer Security (**[DTLS](https://developer.mozilla.org/en-US/docs/Glossary/DTLS)**) transport state.

## Syntax

    let myState = dtlsTransport.state;

### Value

A string whose value is taken from the `RTCDtlsTransportState` enumerated type. Its value is one of the following:

`new`  
The initial state when DTLS has not started negotiating yet.

`connecting`  
DTLS is in the process of negotiating a secure connection and verifying the remote fingerprint.

`connected`  
DTLS has completed negotiation of a secure connection and verified the remote fingerprint.

`closed`  
The transport has been closed intentionally as the result of receipt of a `close_notify` alert, or calling [`RTCPeerConnection.close()`](../rtcpeerconnection/close).

`failed`  
The transport has failed as the result of an error (such as receipt of an error alert or failure to validate the remote fingerprint).

## Examples

This example presents a function, `tallySenders()`, which iterates over an `RTCPeerConnection`'s [`RTCRtpSender`](../rtcrtpsender)s, tallying up how many of them are in various states. The function returns an object containing properties whose values indicate how many of the senders are in each state.

    let pc = new RTCPeerConnection({ bundlePolicy: "max-bundle" });

    /* ... */

    function tallySenders(pc) {
      let results = {
        transportMissing: 0,
        connectionPending: 0,
        connected: 0,
        closed: 0,
        failed: 0,
        unknown: 0
      };

      let senderList = pc.getSenders();
      senderList.forEach(sender => {
        let transport = sender.transport;

        if (!transport) {
          results.transportMissing++;
        } else {
          switch(transport.state) {
            case "new":
            case "connecting":
              results.connectionPending++;
              break;
           case "connected":
              results.connected++;
              break;
           case "closed":
              results.closed++;
              break;
           case "failed":
              results.failed++;
              break;
           default:
              results.unknown++;
              break;
          }
        }
      });
      return results;
    }

Note that in this code, the `new` and `connecting` states are being treated as a single `connectionPending` status in the returned object.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcdtlstransport-state">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCDtlsTransport.state' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`state`

72

12

No

See [bug 1307996](https://bugzil.la/1307996).

No

60

No

72

72

No

See [bug 1307996](https://bugzil.la/1307996).

50

No

11.0

## See also

- [WebRTC API](../webrtc_api)
- [`RTCDtlsTransport`](../rtcdtlstransport)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDtlsTransport/state" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCDtlsTransport/state</a>
