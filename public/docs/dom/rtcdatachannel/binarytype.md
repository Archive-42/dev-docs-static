# RTCDataChannel.binaryType

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Draft**

This page is not complete.

The property `binaryType` on the [`RTCDataChannel`](../rtcdatachannel) interface is a [`DOMString`](../domstring) which specifies the type of JavaScript object which should be used to represent binary data received on the [`RTCDataChannel`](../rtcdatachannel). Values allowed by the [`WebSocket.binaryType`](../websocket/binarytype) property are also permitted here: `"blob"` if [`Blob`](../blob) objects are being used or `"arraybuffer"` if [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) objects are being used. The default is `"blob"`.

When a binary message is received on the data channel, the resulting `message` event's [`MessageEvent.data`](../messageevent/data) property is an object of the type specified by the `binaryType`.

## Syntax

    var type = aDataChannel.binaryType;

    aDataChannel.binaryType = type;

### Value

A [`DOMString`](../domstring) that can have one of these values:

`"blob"`  
Received binary messages' contents will be contained in [`Blob`](../blob) objects.

`"arraybuffer"`  
Received binary messages' contents will be contained in [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) objects.

## Example

This code configures a data channel to receive binary data in [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) objects, and establishes a listener for `message` events which constructs a string representing the received data as a list of hexadecimal byte values.

    var dc = peerConnection.createDataChannel("Binary");
    dc.binaryType = "arraybuffer";

    dc.onmessage = function(event) {
      let byteArray = new Uint8Array(event.data);
      let hexString = "";

      byteArray.forEach(function(byte) {
        hexString += byte.toString(16) + " ";
      });
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-datachannel-binarytype">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCDataChannel.binaryType' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`binaryType`

Yes

≤79

18

No

Yes

11

4.4

29

18

Yes

11

2.0

## See also

- [WebRTC](../webrtc_api)
- [Using WebRTC data channels](../webrtc_api/using_data_channels)
- [`RTCDataChannel`](../rtcdatachannel)
- [`RTCDataChannel.send()`](send)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/binaryType" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/binaryType</a>
