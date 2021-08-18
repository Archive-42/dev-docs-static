RTCDataChannel.label
====================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The read-only `RTCDataChannel` property `label` returns a [`DOMString`](../domstring) containing a name describing the data channel. These labels are not required to be unique.

You may use the label as you wish; you could use it to identify all the channels that are being used for the same purpose, by giving them all the same name. Or you could give each channel a unique label for tracking purposes. It's entirely up to the design decisions made when building your site or app.

A unique ID can be found in the [`id`](id) property.

A data channel's label is set when the channel is created by calling [`RTCPeerConnection.createDataChannel()`](../rtcpeerconnection/createdatachannel). It cannot be changed after that.

Syntax
------

    var name = aDataChannel.label;

### Value

A string identifier assigned by the Web site or app when the data channel was created, as specified when [`RTCPeerConnection.createDataChannel()`](../rtcpeerconnection/createdatachannel) was called to create the channel.

Example
-------

This sample creates a data channel on an [`RTCPeerConnection`](../rtcpeerconnection), then, some time later, sets the content of a UI element to display the channel's name.

    var pc = new RTCPeerConnection();
    var dc = pc.createDataChannel("my channel");

    /* ... */

    document.getElementById("channel-name").innerHTML =
              "<span class='channelName'>" + dc.label + "</span>";

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-datachannel-label">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCDataChannel.label' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`label`

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
-   [`RTCDataChannel.id`](id)
-   [`RTCPeerConnection.createDataChannel()`](../rtcpeerconnection/createdatachannel)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/label" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/label</a>
