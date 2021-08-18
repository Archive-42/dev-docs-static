# RTCDataChannel.onopen

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `RTCDataChannel.onopen` property is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) which specifies a function to be called when the `open` event is fired; this is a simple [`Event`](../event) which is sent when the data channel's underlying data transport—the link over which the [`RTCDataChannel`](../rtcdatachannel)'s messages flow—is established or re-established.

## Syntax

    RTCDataChannel.onopen = function;

### Value

A function which the browser will call to handle the `open` event. The function receives as its only input parameter the event itself, of type [`Event`](../event).

## Example

This example adds a new data channel to an existing [`RTCPeerConnection`](../rtcpeerconnection), `myPeerConnection`. It then establishes an `open` event handler which updates some user interface elements to prepare them for being used to send messages over the data channel.

    let dc = myPeerConnection.createDataChannel("Message Channel");

    dc.onopen = function(event) {
      let messageBox = document.getElementById("messageBox");
      let sendButton = document.getElementById("sendButton");

      messageBox.disabled = false;
      messageBox.focus();
      sendButton.disabled = false;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcdatachannel-onopen">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCDataChannel.onopen' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

## Browser compatibility

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

`onopen`

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

## See also

- [WebRTC](../webrtc_api)
- The `open` event and its type, [`Event`](../event).
- [`RTCDataChannel.onclose`](onclose)
- The `close` event and its type, [`Event`](../event).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/onopen" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/onopen</a>
