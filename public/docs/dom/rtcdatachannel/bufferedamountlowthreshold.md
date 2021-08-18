# RTCDataChannel.bufferedAmountLowThreshold

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `RTCDataChannel` property `bufferedAmountLowThreshold` is used to specify the number of bytes of buffered outgoing data that is considered "low." The default value is 0. When the number of buffered outgoing bytes, as indicated by the [`bufferedAmount`](bufferedamount) property, falls to or below this value, a `bufferedamountlow` event is fired. This event may be used, for example, to implement code which queues more messages to be sent whenever there's room to buffer them. Listeners may be added with [`onbufferedamountlow`](onbufferedamountlow) or [`addEventListener()`](../eventtarget/addeventlistener).

The user agent may implement the process of actually sending data in any way it chooses; this may be done periodically during the event loop or truly asynchronously. As messages are actually sent, this value is reduced accordingly.

`bufferedamountlow `events are not fired after the data channel is closed.

## Syntax

    var threshold = aDataChannel.bufferedAmountLowThreshold;

    aDataChannel.bufferedAmountLowThreshold = threshold;

### Value

The number of queued outgoing data bytes below which the buffer is considered to be "low."

## Example

In this snippet of code, `bufferedAmountLowThreshold` is set to 64kB, and a handler for the `bufferedamountlow` event is established by setting the [`RTCDataChannel.onbufferedamountlow`](onbufferedamountlow) property to a function which should send more data into the buffer by calling [`send()`](send).

    var dc = peerConnection.createDataChannel("File Transfer");
    dc.bufferedAmountLowThreshold = 65535;

    dc.onbufferedamountlow = function() {
      /* use send() to queue more data to be sent */
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcdatachannel-bufferedamountlowthreshold">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCDataChannel.bufferedAmountLowThreshold' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`bufferedAmountLowThreshold`

56

≤79

Yes

No

43

11

56

56

No

43

11

6.0

## See also

- [WebRTC](../webrtc_api)
- [Using WebRTC data channels](../webrtc_api/using_data_channels)
- [`RTCDataChannel`](../rtcdatachannel)
- [`RTCDataChannel.bufferedAmount`](bufferedamount)
- `bufferedamountlow` event
- [`RTCDataChannel.onbufferedamountlow`](onbufferedamountlow)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/bufferedAmountLowThreshold" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/bufferedAmountLowThreshold</a>
