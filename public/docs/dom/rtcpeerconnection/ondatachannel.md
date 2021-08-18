RTCPeerConnection.ondatachannel
===============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `RTCPeerConnection.ondatachannel` property is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) which specifies a function which is called when the `datachannel` event occurs on an [`RTCPeerConnection`](../rtcpeerconnection). This event, of type [`RTCDataChannelEvent`](../rtcdatachannelevent), is sent when an [`RTCDataChannel`](../rtcdatachannel) is added to the connection by the remote peer calling [`createDataChannel()`](createdatachannel).

At the time this event is received, the [`RTCDataChannel`](../rtcdatachannel) it indicates may not yet actually be open. Be sure to wait for the `"open"` event to be fired on the new `RTCDataChannel` before using it.

Syntax
------

    RTCPeerConnection.ondatachannel = function;

### Value

Set this property to be a function you provide which receives as input a single parameter: an [`RTCDataChannelEvent`](../rtcdatachannelevent) which provides in its `channel` property the [`RTCDataChannel`](../rtcdatachannel) which has been created.

Example
-------

    pc.ondatachannel = function(ev) {
      console.log('Data channel is created!');
      ev.channel.onopen = function() {
        console.log('Data channel is open and ready to be used.');
      };
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcpeerconnection-ondatachannel">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCPeerConnection.ondatachannel' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`ondatachannel`

25

79

22

No

43

Promise-based version.

37-43

11

≤37

25

44

43

Promise-based version.

37-43

11

6.0

See also
--------

-   The `datachannel` event and its type, [`RTCDataChannelEvent`](../rtcdatachannelevent).
-   [`RTCPeerConnection.createDataChannel()`](createdatachannel)
-   [A simple RTCDataChannel sample](../webrtc_api/simple_rtcdatachannel_sample)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/ondatachannel" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/ondatachannel</a>
