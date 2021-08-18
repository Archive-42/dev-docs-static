RTCPeerConnection.close()
=========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `RTCPeerConnection.close()` method closes the current peer connection.

Syntax
------

    peerConnection.close();

*This method has no parameters, and returns nothing.*

Calling this method terminates the RTCPeerConnection's ICE agent, ending any ongoing ICE processing and any active streams. This also releases any resources in use by the ICE agent, including TURN permissions. All [`RTCRtpSender`](../rtcrtpsender) objects are considered to be stopped once this returns (they may still be in the process of stopping, but for all intents and purposes, they're stopped).

Once this method returns, the signaling state as returned by [`RTCPeerConnection.signalingState`](signalingstate) is `closed`.

Make sure that you `delete` all references to the previous [`RTCPeerConnection`](../rtcpeerconnection) before attempting to create a new one that connects to the same remote peer, as not doing so might result in some errors depending on the browser.

Example
-------

    var pc = new RTCPeerConnection();
    var dc = pc.createDataChannel("my channel");

    dc.onmessage = function (event) {
      console.log("received: " + event.data);
      pc.close(); // We decided to close after the first received message
    };

    dc.onopen = function () {
      console.log("datachannel open");
    };

    dc.onclose = function () {
      console.log("datachannel close");
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcpeerconnection-close">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCPeerConnection.close()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`close`

23

15

Yes

No

Yes

11

≤37

Yes

Yes

Yes

11

Yes

See also
--------

-   [WebRTC](../webrtc_api)
-   [`RTCPeerConnection`](../rtcpeerconnection)
-   [`RTCPeerConnection.signalingState`](signalingstate)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/close" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/close</a>
