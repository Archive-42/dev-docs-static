# RTCDataChannel.negotiated

The read-only `RTCDataChannel` property `negotiated` indicates whether the [`RTCDataChannel`](../rtcdatachannel)'s connection was negotiated by the Web app (`true`) or by the WebRTC layer (`false`). `false`

See [Creating a data channel](#) in [Using WebRTC data channels](../webrtc_api/using_data_channels) for further information about this property.

## Syntax

    var negotiated = aDataChannel.negotiated;

### Value

`true` if the [`RTCDataChannel`](../rtcdatachannel)'s connection was negotiated by the Web app itself; `false` if the negotiation was handled by the WebRTC layer. The default is `false`.

## Example

The code snippet below checks the value of `negotiated`; if it's `true`, a function called `shutdownRemoteChannel()` is called with the channel's [`id`](id); presumably this would be implemented to transmit a shutdown signal to the remote peer prior to terminating the connection.

    if (dataChannel.negotiated) {
      shutdownRemoteChannel(dataChannel.id);
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-datachannel-negotiated">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCDataChannel.negotiated' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`negotiated`

56

≤79

68

No

43

11

56

56

68

43

11

6.0

## See also

- [WebRTC](../webrtc_api)
- [Using WebRTC data channels](../webrtc_api/using_data_channels)
- [`RTCDataChannel`](../rtcdatachannel)
- [`RTCPeerConnection.createDataChannel()`](../rtcpeerconnection/createdatachannel)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/negotiated" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/negotiated</a>
