# RTCDataChannelEvent.channel

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The read-only property ` RTCDataChannelEvent``.channel ` returns the [`RTCDataChannel`](../rtcdatachannel) associated with the event.

## Syntax

     var channel = RTCDataChannelEvent.channel;

### Value

A [`RTCDataChannel`](../rtcdatachannel) object representing the data channel linking the receiving [`RTCPeerConnection`](../rtcpeerconnection) to its remote peer.

## Example

The first line of code in the `datachannel` event handler shown below takes the channel from the event object and saves it locally for use by the code handling data traffic.

    pc.ondatachannel = function(event) {
      inboundDataChannel = event.channel;
      inboundDataChannel.onmessage = handleIncomingMessage;
      inboundDataChannel.onopen = handleChannelOpen;
      inboundDataChannel.onclose = handleChannelClose;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-datachannelevent-channel">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCDataChannelEvent.channel' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`channel`

Yes

≤79

22

No

Yes

11

Yes

28

22

Yes

11

1.5

## See also

- `datachannel`
- [`RTCDataChannel`](../rtcdatachannel)
- [`RTCPeerConnection.ondatachannel`](../rtcpeerconnection/ondatachannel)
- [A simple RTCDataChannel sample](../webrtc_api/simple_rtcdatachannel_sample)
- [`RTCPeerConnection`](../rtcpeerconnection)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannelEvent/channel" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannelEvent/channel</a>
