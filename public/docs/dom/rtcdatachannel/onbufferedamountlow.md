# RTCDataChannel.onbufferedamountlow

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `RTCDataChannel.onbufferedamountlow` property is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) which specifies a function the browser calls when the `bufferedamountlow` event is sent to the [`RTCDataChannel`](../rtcdatachannel). This event, which is represented by a simple [`Event`](../event) object, is sent when the amount of data buffered to be sent falls to or below the threshold specified by the channel's [`bufferedAmountLowThreshold`](bufferedamountlowthreshold).

See [Buffering](../webrtc_api/using_data_channels#buffering) in [Using WebRTC data channels](../webrtc_api/using_data_channels) to learn more about how to work with the data channel buffer.

## Syntax

    RTCDataChannel.onbufferedamountlow = function;

### Value

A function which the browser will call to handle the `bufferedamountlow` event. This function receives as its only input parameter a simple [`Event`](../event) object representing the event which has occurred.

## Example

This example responds to the `bufferedamountlow` event by fetching up to 64kB of a file represented by an object `source` and calling [`RTCDataChannel.send()`](send) to queue up the retrieved data for sending on the data channel.

    pc = new RTCPeerConnection();
    dc = pc.createDataChannel("SendFile");

    /* ... */

    dc.onbufferedamountlow = function() {
      if (source.position <= source.length) {
        dc.send(source.readFile(65536));
      }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcdatachannel-onbufferedamountlow">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCDataChannel.onbufferedamountlow' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`onbufferedamountlow`

57

The default for `rtcpMuxPolicy` is `require`.

≤79

The default for `rtcpMuxPolicy` is `require`.

Yes

No

44

The default for `rtcpMuxPolicy` is `require`.

11

57

The default for `rtcpMuxPolicy` is `require`.

57

The default for `rtcpMuxPolicy` is `require`.

Yes

43

The default for `rtcpMuxPolicy` is `require`.

11

7.0

The default for `rtcpMuxPolicy` is `require`.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/onbufferedamountlow" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/onbufferedamountlow</a>
