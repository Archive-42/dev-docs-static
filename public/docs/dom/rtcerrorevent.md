# RTCErrorEvent

The WebRTC API's `RTCErrorEvent` interface represents an error sent to a WebRTC object. It's based on the standard [`Event`](event) interface, but adds RTC-specific information describing the error, as shown below.

## Constructor

<span class="page-not-created">`RTCErrorEvent()`</span>  
Creates and returns a new `RTCErrorEvent` object.

## Properties

_In addition to the standard properties available on the [`Event`](event) interface, `RTCErrorEvent` also includes the following:_

[`error`](rtcerrorevent/error) <span class="badge inline readonly">Read only </span>  
An [`RTCError`](rtcerror) object specifying the error which occurred; this object includes the type of error that occurred, information about where the error occurred (such as which line number in the [SDP](https://developer.mozilla.org/en-US/docs/Glossary/SDP) or what [SCTP](https://developer.mozilla.org/en-US/docs/Glossary/SCTP) cause code was at issue).

## Methods

_No additional methods are provided beyond any found on the parent interface, [`Event`](event)._

## Description

There are other data types used for error events in WebRTC, as needed for errors with special information sharing requirements. The most common of these is probably [`RTCPeerConnectionIceErrorEvent`](rtcpeerconnectioniceerrorevent), used by the [`icecandidateerror`](rtcpeerconnection/icecandidateerror_event) event, which signals an error that has occurred while gathering ICE candidates during connection negotiation.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcerrorevent">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCErrorEvent' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`RTCErrorEvent`

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

## See also

- WebRTC API
- [`RTCError`](rtcerror)
- The `error` event occurs on the following interfaces: [`RTCDataChannel`](rtcdatachannel) and [`RTCDtlsTransport`](rtcdtlstransport)
- [`RTCPeerConnectionIceErrorEvent`](rtcpeerconnectioniceerrorevent)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCErrorEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCErrorEvent</a>
