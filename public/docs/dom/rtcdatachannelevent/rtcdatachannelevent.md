# RTCDataChannelEvent()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `RTCDataChannelEvent()` constructor creates a new [`RTCDataChannelEvent`](../rtcdatachannelevent).

You will rarely if ever construct an `RTCDataChannelEvent` by hand; these events are normally created and sent by the WebRTC layer itself.

## Syntax

     var event = new RTCDataChannelEvent(type, rtcDataChannelEventInit);

### Parameters

`type`  
A [`DOMString`](../domstring) which specifies the name of the event. There is only one type of `RTCDataChannelEvent`, so this will always be `"datachannel"`.

`rtcDataChannelEventInit`  
A `RTCDataChannelEventInit` dictionary, which has following fields:

- `"channel"` of type [`RTCDataChannel`](../rtcdatachannel), representing the data channel being concerned by the event.
- `"bubbles"`, optional, inherited from `EventInit`. Indicates if the event must bubble or not. `false`.
- `"cancelable"`, optional, inherited from `EventInit`. Indicates if the event can be canceled or not. **Default is false.**

### Value

A new [`RTCDataChannelEvent`](../rtcdatachannelevent) configured as specified.

## Example

In this example, a new `datachannel` event is created. `dc` is a data channel which already exists.

    var event = new RTCDataChannelEvent("datachannel", {"channel": dc});

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcdatachannelevent">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCDataChannelEvent' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`RTCDataChannelEvent`

57

≤79

22

No

44

11

57

57

22

43

11

7.0

## See also

- [WebRTC](../webrtc_api)
- [`RTCDataChannel`](../rtcdatachannel)
- [`RTCPeerConnection`](../rtcpeerconnection)
- [A simple RTCDataChannel sample](../webrtc_api/simple_rtcdatachannel_sample)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannelEvent/RTCDataChannelEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannelEvent/RTCDataChannelEvent</a>
