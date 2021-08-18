RTCDataChannel.ordered
======================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The read-only `RTCDataChannel` property `ordered` indicates whether or not the data channel guarantees in-order delivery of messages; the default is `true`, which indicates that the data channel is indeed ordered. This is set when the [`RTCDataChannel`](../rtcdatachannel) is created, by setting the `ordered` property on the `RTCDataChannelInit` object passed as [`RTCPeerConnection.createDataChannel()`](../rtcpeerconnection/createdatachannel)'s `options` parameter.

Syntax
------

    var ordered = aDataChannel.ordered;

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) value which is `true` if in-order delivery is guaranteed and is otherwise `false`.

Example
-------

    var pc = new RTCPeerConnection();
    var dc = pc.createDataChannel("my channel");

    if (!dc.ordered) {
      // Handle unordered messaging
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-datachannel-ordered">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCDataChannel.ordered' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`ordered`

56

≤79

Yes

No

43

11

56

56

Yes

43

11

6.0

See also
--------

-   [WebRTC](../webrtc_api)
-   [`RTCDataChannel`](../rtcdatachannel)
-   [`RTCPeerConnection.createDataChannel()`](../rtcpeerconnection/createdatachannel)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/ordered" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/ordered</a>
