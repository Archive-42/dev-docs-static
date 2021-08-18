# RTCDataChannel.maxRetransmits

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The read-only `RTCDataChannel` property `maxRetransmits` returns the maximum number of times the browser should try to retransmit a message before giving up, as set when the data channel was created, or `null`, which indicates that there is no maximum. This can only be set when the [`RTCDataChannel`](../rtcdatachannel) is created by calling [`RTCPeerConnection.createDataChannel()`](../rtcpeerconnection/createdatachannel), using the `maxRetransmits` field in the specified `options`.

## Syntax

    var tries = aDataChannel.maxRetransmits;

### Value

The maximum number of times the browser will try to retransmit a message before giving up, or `null` if not set when [`RTCPeerConnection.createDataChannel()`](../rtcpeerconnection/createdatachannel) was called. The default is `null`.

## Example

    // TBD

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-datachannel-maxretransmits">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCDataChannel.maxRetransmits' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`maxRetransmits`

56

≤79

62

No

43

11

56

56

62

43

11

6.0

## See also

- [WebRTC](../webrtc_api)
- [`RTCDataChannel`](../rtcdatachannel)
- [`RTCDataChannel.maxPacketLifetime`](maxpacketlifetime)
- [`RTCPeerConnection.createDataChannel()`](../rtcpeerconnection/createdatachannel)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/maxRetransmits" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/maxRetransmits</a>
