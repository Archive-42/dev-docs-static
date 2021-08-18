# RTCDataChannel.bufferedAmount

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The read-only `RTCDataChannel` property `bufferedAmount` returns the number of bytes of data currently queued to be sent over the data channel. The queue may build up as a result of calls to the [`send()`](send) method. This only includes data buffered by the user agent itself; it doesn't include any framing overhead or buffering done by the operating system or network hardware.

The user agent may implement the process of actually sending data in any way it chooses; this may be done periodically during the event loop or truly asynchronously. As messages are actually sent, this value is reduced accordingly.

Closing the data channel doesn't reset this count, even though the user agent purges the queued messages. However, even after closing the channel, attempts to send messages continue to add to the `bufferedAmount` value, even though the messages are neither sent nor buffered.

Whenever this value decreases to fall to or below the value specified in the [`bufferedAmountLowThreshold`](bufferedamountlowthreshold) property, the user agent fires the `bufferedamountlow` event. This event may be used, for example, to implement code which queues more messages to be sent whenever there's room to buffer them.

## Syntax

    var amount = aDataChannel.bufferedAmount;

### Value

The number of bytes of data currently queued to be sent over the data channel but have not yet been sent.

## Example

The snippet below includes a function which changes the contents of a block with the ID "bufferSize" to a string indicating the number of bytes currently buffered on an [`RTCDataChannel`](../rtcdatachannel).

    var dc = peerConnection.createDataChannel("File Transfer");

    /* ... */

    function showBufferedAmount(channel) {
      let el = document.getElementById("bufferSize");

      el.innerHTML = channel.bufferedAmount + " bytes";
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-datachannel-bufferedamount">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCDataChannel.bufferedAmount' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`bufferedAmount`

56

≤79

18

No

43

11

56

56

18

43

11

6.0

## See also

- [WebRTC](../webrtc_api)
- [Using WebRTC data channels](../webrtc_api/using_data_channels)
- [`RTCDataChannel`](../rtcdatachannel)
- [`RTCDataChannel.bufferedAmountLowThreshold`](bufferedamountlowthreshold)
- `bufferedamountlow` event
- [`RTCDataChannel.onbufferedamountlow`](onbufferedamountlow)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/bufferedAmount" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/bufferedAmount</a>
