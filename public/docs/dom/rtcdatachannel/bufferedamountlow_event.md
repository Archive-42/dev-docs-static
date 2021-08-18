# RTCDataChannel: bufferedamountlow event

A `bufferedamountlow` event is sent to an [`RTCDataChannel`](../rtcdatachannel) when the number of bytes currently in the outbound data transfer buffer falls below the threshold specified in [`bufferedAmountLowThreshold`](bufferedamountlowthreshold). `bufferedamountlow` events aren't sent if `bufferedAmountLowThreshold` is 0.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onbufferedamountlow"><code>onbufferedamountlow</code></a></td></tr></tbody></table>

## Examples

This example sets up a handler for `bufferedamountlow` to request more data any time the data channel's buffer falls below the number of bytes specified by [`bufferedAmountLowThreshold`](bufferedamountlowthreshold), which we have set to 65536. In other words, we'll try to keep at least 64kB of data in the buffer, reading 64kB at a time from the source.

    let pc = new RTCPeerConnection();
    let dc = pc.createDataChannel("SendFile");
    let source = /* source data object */

    dc.bufferedAmountLowThreshold = 65536;

    pc.addEventListener("bufferedamountlow", ev => {
      if (source.position <= source.length) {
        dc.send(source.readFile(65536));
      }
    }, false);

After creating the `RTCPeerConnection`, this calls [`RTCPeerConnection.createDataChannel()`](../rtcpeerconnection/createdatachannel) to create the data channel. Then a listener is created for `bufferedamountlow` to refill the incoming data buffer any time its contents fall below 65536 bytes.

You can also set up a listener for `bufferedamountlow` using its event handler property, [`onbufferedamountlow`](onbufferedamountlow):

    pc.onbufferedamountlow = ev => {
      if (source.position <= source.length) {
        dc.send(source.readFile(65536));
      }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#event-datachannel-bufferedamountlow">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'bufferedamountlow' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`bufferedamountlow_event`

57

The default for `rtcpMuxPolicy is require.`

≤79

The default for `rtcpMuxPolicy is require.`

Yes

No

44

The default for `rtcpMuxPolicy is require.`

Yes

57

The default for `rtcpMuxPolicy is require.`

57

The default for `rtcpMuxPolicy is require.`

Yes

43

The default for `rtcpMuxPolicy is require.`

No

7.0

The default for `rtcpMuxPolicy is require.`

## See also

- [WebRTC API](../webrtc_api)
- [`RTCDataChannel`](../rtcdatachannel)
- [`RTCDataChannel.onbufferedamountlow`](onbufferedamountlow)
- [`RTCDataChannel.bufferedAmountLowThreshold`](bufferedamountlowthreshold)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/bufferedamountlow_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/bufferedamountlow_event</a>
