RTCDataChannel.id
=================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The read-only `RTCDataChannel` property `id` returns an ID number (between 0 and 65,534) which uniquely identifies the [`RTCDataChannel`](../rtcdatachannel). This ID is set at the time the data channel is created, either by the user agent (if [`RTCDataChannel.negotiated`](negotiated) is `false`) or by the site or app script (if `negotiated` is `true`).

Each [`RTCPeerConnection`](../rtcpeerconnection) can therefore have up to a theoretical maximum of 65,534 data channels on it, although the actual maximum may vary from browser to browser.

In early versions of the WebRTC specification, this property's name was [`stream`](stream). Code that uses that property needs to be updated.

Syntax
------

    var id = aDataChannel.id;

### Value

An `unsigned short` value (that is, an integer between 0 and 65,535) which uniquely identifies the data channel.

While the [`label`](label) property doesn't have to be unique, this ID number is guaranteed to be unique among all data channels. Additionally, known implementations of WebRTC use the same ID on both peers. A unique ID makes it easier for your code to do its own out-of-band data channel-related signaling.

This can be also useful for logging and debugging purposes.

Example
-------

    var pc = new RTCPeerConnection();
    var dc = pc.createDataChannel("my channel");

    console.log("Channel id: " + dc.id);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcdatachannel-id">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCDataChannel.id' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`id`

56

≤79

No

No

43

11

56

56

No

43

11

6.0

See also
--------

-   [WebRTC](../webrtc_api)
-   [`RTCDataChannel`](../rtcdatachannel)
-   [`RTCPeerConnection.createDataChannel()`](../rtcpeerconnection/createdatachannel)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/id" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/id</a>
