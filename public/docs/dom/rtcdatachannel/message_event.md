RTCDataChannel: message event
=============================

The WebRTC `message` event is sent to the [`onmessage`](onmessage) event handler on an [`RTCDataChannel`](../rtcdatachannel) object when a message has been received from the remote peer.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../messageevent"><code>MessageEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onmessage"><code>onmessage</code></a></td></tr></tbody></table>

**Note:** The `message` event uses as its event object type the [`MessageEvent`](../messageevent) interface defined by the HTML specification.

Examples
--------

For a given [`RTCDataChannel`](../rtcdatachannel), `dc`, created for a peer connection using its [`createDataChannel()`](../rtcpeerconnection/createdatachannel) method, this code sets up a handler for incoming messages and acts on them by adding the data contained within the message to the current document as a new [`<p>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p) (paragraph) element.

    dc.addEventListener("message", ev => {
      let newParagraph = document.createElement("p");
      let textNode = document.createTextNode(event.data);
      newParagraph.appendChild(textNode);

      document.body.appendChild(newParagraph);
    }, false);

Lines 2-4 create the new paragraph element and add the message data to it as a new text node. Line 6 appends the new paragraph to the end of the document's body.

You can also use an `RTCDataChannel` object's [`onmessage`](onmessage) event handler property to set the event handler:

    dc.onmessage = ev => {
      let newParagraph = document.createElement("p");
      let textNode = document.createTextNode(event.data);
      newParagraph.appendChild(textNode);

      document.body.appendChild(newParagraph);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#event-datachannel-message">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'the &lt;code&gt;message&lt;/code&gt; event' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`message_event`

56

≤79

Yes

No

43

Yes

56

56

Yes

43

Yes

6.0

See also
--------

-   [WebRTC API](../webrtc_api)
-   [A simple RTCDataChannel example](../webrtc_api/simple_rtcdatachannel_sample)
-   Related events: [`open`](open_event), [`close`](close_event), and [`error`](error_event)
-   [`RTCDataChannel.send()`](send)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/message_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/message_event</a>
