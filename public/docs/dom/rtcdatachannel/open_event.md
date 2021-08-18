RTCDataChannel: open event
==========================

The WebRTC `open` event is sent to an [`RTCDataChannel`](../rtcdatachannel) object's [`onopen`](onopen) event handler when the underlying transport used to send and receive the data channel's messages is opened or re-opened.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../rtcdatachannelevent"><code>RTCDataChannelEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onopen"><code>onopen</code></a></td></tr></tbody></table>

Examples
--------

This example adds to the [`RTCDataChannel`](../rtcdatachannel) `dc` a handler for the `open` event that adjusts the user interface to indicate that a chat window is ready to be used after a connection has been established. It enables the message input box and send button as well as enabling the disconnect button and disabling the connect button. Finally, the message input box is focused so the user can immediately begin to type.

    dc.addEventListener("open", ev => {
      messageInputBox.disabled = false;
      sendMessageButton.disabled = false;
      disconnectButton.disabled = false;
      connectButton.disabled = true;

      messageInputBox.focus();

    }, false);

This can also be done by directly setting the value of the channel's [`onopen`](onopen) event handler property.

    dc.onopen = ev => {
      messageInputBox.disabled = false;
      sendMessageButton.disabled = false;
      disconnectButton.disabled = false;
      connectButton.disabled = true;

      messageInputBox.focus();
    }

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

`open_event`

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
-   Related events: [`message`](message_event), [`close`](close_event), and [`error`](error_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/open_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/open_event</a>
