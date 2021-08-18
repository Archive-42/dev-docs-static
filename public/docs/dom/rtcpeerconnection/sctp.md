RTCPeerConnection.sctp
======================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The read-only `sctp` property on the [`RTCPeerConnection`](../rtcpeerconnection) interface returns an [`RTCSctpTransport`](../rtcsctptransport) describing the [SCTP](https://developer.mozilla.org/en-US/docs/Glossary/SCTP) transport over which SCTP data is being sent and received. If SCTP hasn't been negotiated, this value is `null`.

The SCTP transport is used for transmitting and receiving data for any and all [`RTCDataChannel`](../rtcdatachannel)s on the peer connection.

Syntax
------

    var sctp = RTCPeerConnection.sctp;

### Value

A [`RTCSctpTransport`](../rtcsctptransport) object describing the SCTP transport being used by the [`RTCPeerConnection`](../rtcpeerconnection) for transmitting and receiving on its data channels, or `null` if SCTP negotiation hasn't happened.

Example
-------

    var pc = new RTCPeerConnection();

    var channel = pc.createDataChannel("Mydata");
    channel.onopen = function(event) {
      channel.send('sending a message');
    }
    channel.onmessage = function(event) {
      console.log(event.data);
    }

    // Determine the largest message size that can be sent

    var sctp = pc.sctp;
    var maxMessageSize = sctp.maxMessageSize;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcpeerconnection-sctp">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCPeerConnection.sctp' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`sctp`

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

-   [WebRTC](../webrtc_api)
-   [`RTCPeerConnection`](../rtcpeerconnection)
-   [`RTCDataChannel`](../rtcdatachannel)
-   [SCTP](https://developer.mozilla.org/en-US/docs/Glossary/SCTP)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/sctp" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/sctp</a>
