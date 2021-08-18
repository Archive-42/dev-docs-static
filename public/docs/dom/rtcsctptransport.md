RTCSctpTransport
================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `RTCSctpTransport` interface provides information which describes a Stream Control Transmission Protocol (**[SCTP](https://developer.mozilla.org/en-US/docs/Glossary/SCTP)**) transport. This provides information about limitations of the transport, but also provides a way to access the underlying Datagram Transport Layer Security (**[DTLS](https://developer.mozilla.org/en-US/docs/Glossary/DTLS)**) transport over which SCTP packets for all of an [`RTCPeerConnection`](rtcpeerconnection)'s data channels are sent and received.

You don't create [`RTCSctpTransport`](rtcsctptransport) objects yourself; instead, you get access to the `RTCSctpTransport` for a given `RTCPeerConnection` through its **[`sctp`](rtcpeerconnection/sctp)** property.

Possibly the most useful property on this interface is its <span class="page-not-created">`maxMessageSize`</span> property, which you can use to determine the upper limit on the size of messages you can send over a data channel on the peer connection.

Properties
----------

*Also inherits properties from: [`EventTarget`](eventtarget)*

 <span class="page-not-created">`RTCSctpTransport.maxChannels`</span><span class="badge inline readonly">Read only </span>   
An integer value indicating the maximum number of [`RTCDataChannel`s](rtcdatachannel) that can be open simultaneously.

 <span class="page-not-created">`RTCSctpTransport.maxMessageSize`</span><span class="badge inline readonly">Read only </span>   
An integer value indicating the maximum size, in bytes, of a message which can be sent using the [`RTCDataChannel.send()`](rtcdatachannel/send) method.

 [`RTCSctpTransport.state`](rtcsctptransport/state)<span class="badge inline readonly">Read only </span>   
A [`DOMString`](domstring) enumerated value indicating the state of the SCTP transport.

 <span class="page-not-created">`RTCSctpTransport.transport`</span><span class="badge inline readonly">Read only </span>   
An [`RTCDtlsTransport`](rtcdtlstransport) object representing the [DTLS](https://developer.mozilla.org/en-US/docs/Glossary/DTLS) transport used for the transmission and receipt of data packets.

### Event handlers

<span class="page-not-created">`RTCSctpTransport.onstatechange`</span>  
Fired when the [`RTCSctpTransport.state`](rtcsctptransport/state) changes.

Methods
-------

*This interface has no methods, but inherits methods from: [`EventTarget`](eventtarget)*

Example
-------

TBD

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#rtcsctptransport-interface">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCSctpTransport' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`RTCSctpTransport`

76

79

No

See [bug 1278299](https://bugzil.la/1278299).

No

No

No

76

76

No

See [bug 1278299](https://bugzil.la/1278299).

54

No

12.0

`maxChannels`

76

79

No

See [bug 1278299](https://bugzil.la/1278299).

No

No

No

76

76

No

See [bug 1278299](https://bugzil.la/1278299).

54

No

12.0

`maxMessageSize`

76

79

No

See [bug 1278299](https://bugzil.la/1278299).

No

No

No

76

76

No

See [bug 1278299](https://bugzil.la/1278299).

54

No

12.0

`onstatechange`

76

79

No

See [bug 1278299](https://bugzil.la/1278299).

No

No

No

76

76

No

See [bug 1278299](https://bugzil.la/1278299).

54

No

12.0

`state`

76

79

No

See [bug 1278299](https://bugzil.la/1278299).

No

No

No

76

76

No

See [bug 1278299](https://bugzil.la/1278299).

54

No

12.0

`transport`

76

79

No

See [bug 1278299](https://bugzil.la/1278299).

No

No

No

76

76

No

See [bug 1278299](https://bugzil.la/1278299).

54

No

12.0

See also
--------

-   [WebRTC](webrtc_api)
-   [`RTCPeerConnection`](rtcpeerconnection)
-   [`RTCPeerConnection.sctp`](rtcpeerconnection/sctp)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCSctpTransport" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCSctpTransport</a>
