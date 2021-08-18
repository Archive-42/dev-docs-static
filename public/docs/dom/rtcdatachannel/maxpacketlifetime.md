RTCDataChannel.maxPacketLifeTime
================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The read-only `RTCDataChannel` property `maxPacketLifeTime` returns the amount of time, in milliseconds, the browser is allowed to take to attempt to transmit a message, as set when the data channel was created, or `null`. This limits how long the browser can continue to attempt to transmit and retransmit the message before giving up.

Syntax
------

    var lifetime = aDataChannel.maxPacketLifeTime;

### Value

The number of milliseconds over which the browser may continue to attempt to transmit the message until it either succeeds or gives up. If not set when [`RTCPeerConnection.createDataChannel()`](../rtcpeerconnection/createdatachannel) was called to create the data channel, this value is `null`.

Example
-------

    // TBD

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-datachannel-maxpacketlifetime">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCDataChannel.maxPacketLifeTime' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`maxPacketLifeTime`

56

≤79

62

No

43

11

56

56

62

43

11

6.0

See also
--------

-   [WebRTC](../webrtc_api)
-   [`RTCDataChannel`](../rtcdatachannel)
-   [`RTCDataChannel.maxRetransmits`](maxretransmits)
-   [`RTCPeerConnection.createDataChannel()`](../rtcpeerconnection/createdatachannel)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/maxPacketLifeTime" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/maxPacketLifeTime</a>
