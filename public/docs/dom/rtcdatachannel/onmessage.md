RTCDataChannel.onmessage
========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `RTCDataChannel.onmessage` property stores an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) which specifies a function to be called when the `message` event is fired on the channel. This event is represented by the [`MessageEvent`](../messageevent) interface. This event is sent to the channel when a message is received from the other peer.

Syntax
------

    RTCDataChannel.onmessage = function;

### Value

A function which the browser will call to handle the `message` event. The function receives as its sole input parameter a [`MessageEvent`](../messageevent) object describing the event.

Example
-------

This code snippet creates a peer connection, adds a data channel to it, and starts creating new [`<p>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p) (paragraph) elements each time a message arrives, with the message's contents displayed inside it. The new elements are then attached to the end of the document.

    let pc = new RTCPeerConnection();
    let dc = pc.createDataChannel();

    dc.onmessage = function(event) {
      var el = document.createElement("p");
      var txtNode = document.createTextNode(event.data);

      el.appendChild(txtNode);
      receiveBox.appendChild(el);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcdatachannel-onmessage">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCDataChannel.onmessage' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`onmessage`

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
-   [`RTCPeerConnection`](../rtcpeerconnection)
-   [`RTCDataChannel`](../rtcdatachannel)
-   The `message` event and its type, [`MessageEvent`](../messageevent).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/onmessage" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/onmessage</a>
