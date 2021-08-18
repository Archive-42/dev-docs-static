RTCDataChannel.protocol
=======================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The read-only `RTCDataChannel` property `protocol` returns a [`DOMString`](../domstring) containing the name of the subprotocol in use. If no protocol was specified when the data channel was created, then this property's value is "" (the empty string).

The permitted values of this property are defined by the Web site or app using the data channel.

The ability for each channel to have a defined subprotocol lets your app, for example, use JSON objects as messages on one channel while another channel is plaintext and another is raw binary or even some other format.

Syntax
------

    var subProtocol = aDataChannel.protocol;

### Value

A string identifying the app-defined subprotocol being used for exchanging data on the channel. If none has been established, this is an empty string ("").

Example
-------

    var pc = new RTCPeerConnection();
    var dc = pc.createDataChannel("my channel", {
               protocol: "json"
    });

    function handleChannelMessage(dataChannel, msg) {
      switch(dataChannel.protocol) {
        case "json":
          /* process JSON data */
          break;
        case "raw":
          /* process raw binary data */
          break;
      }
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-datachannel-protocol">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCDataChannel.protocol' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`protocol`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/protocol" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/protocol</a>
