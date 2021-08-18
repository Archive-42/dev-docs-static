RTCDataChannel: close event
===========================

The `close` event is sent to the [`onclose`](onclose) event handler on an [`RTCDataChannel`](../rtcdatachannel) instance when the data transport being used for the data channel has closed. Before any further data can be transferred using `RTCDataChannel`, a new data channel instance must be created.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onclose"><code>RTCDataChannel.onclose</code></a></td></tr></tbody></table>

Examples
--------

This example sets up a handler for the `close` event for the [`RTCDataChannel`](../rtcdatachannel) named `dc`; its responsibility in this example is to update user interface elements to reflect that there is no longer an ongoing call, and to allow a new call to be started.

    dc.addEventListener("close", ev => {
      messageInputBox.disabled = true;
      sendButton.disabled = true;
      connectButton.disabled = false;
      disconnectButton.disabled = true;
    }, false);

All this code does in response to receiving the `close` event is to disable an input box and its "Send" button, and to enable the button used to start a call (while disabling the one that ends a call).

You can also use the [`onclose`](onclose) event handler property to set a handler for `close` events:

    dc.onclose = ev => {
      messageInputBox.disabled = true;
      sendButton.disabled = true;
      connectButton.disabled = false;
      disconnectButton.disabled = true;
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcdatachannel-close">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'close' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`close_event`

56

≤79

Yes

No

43

?

56

56

Yes

43

No

6.0

See also
--------

-   [WebRTC API](../webrtc_api)
-   [A simple RTCDataChannel example](../webrtc_api/simple_rtcdatachannel_sample)
-   Related events: [`open`](open_event), [`message`](message_event), and [`error`](error_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/close_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/close_event</a>
