# RTCDataChannel.stream

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The deprecated (and never part of the official specification) read-only `RTCDataChannel` property `stream` returns an ID number (between 0 and 65,535) which uniquely identifies the [`RTCDataChannel`](../rtcdatachannel). This ID is set at the time the data channel is created, either by the user agent (if [`RTCDataChannel.negotiated`](negotiated) is `false`) or by the site or app script (if `negotiated` is `true`).

This property has been replaced with the [`RTCDataChannel.id`](id) property. If you have code that uses `stream`, you will need to update, since browsers have begun to remove support for `stream`.

## Syntax

    var stream = aDataChannel.stream;

### Value

An `unsigned short` value (that is, an integer between 0 and 65,535) which uniquely identifies the data channel.

## Example

    var dataChannel = pc.createDataChannel("SampleChannel");

    console.log("Data channel stream ID: " + dataChannel.stream);

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

`stream`

56

≤79

No

No

43

No

56

56

No

43

No

6.0

## See also

- [WebRTC](../webrtc_api)
- [Using WebRTC data channels](../webrtc_api/using_data_channels)
- [`RTCDataChannel`](../rtcdatachannel)
- [`RTCDataChannel.id`](id)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/stream" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/stream</a>
