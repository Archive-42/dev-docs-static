# RTCDTMFSender.ontonechange

**Draft**

This page is not complete.

The `ontonechange` property of the [`RTCDTMFSender`](../rtcdtmfsender) interface is used to set the event handler for the `tonechange` event, which is sent to the `RTCDTMFSender` each time a tone begins or ends. The event handler receives as input a single parameter of type [`RTCDTMFToneChangeEvent`](../rtcdtmftonechangeevent), which describes the change.

## Syntax

    RTCDTMFSender.ontonechange = toneChangeHandlerFunction;

### Value

A function which is called when a `tonechange` event is sent to the `RTCDTMFSender`, indicating that a DTMF tone has either started playing, or if all tones have finished playing.

## Example

tbd

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcdtmfsender-ontonechange">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'ontonechange' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`ontonechange`

27

≤79

52

No

Yes

13.1

≤37

27

52

Yes

13.4

1.5

## See also

- [WebRTC API](../webrtc_api)
- [Using DTMF with WebRTC](../webrtc_api/using_dtmf)
- [`RTCDTMFSender`](../rtcdtmfsender)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDTMFSender/ontonechange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCDTMFSender/ontonechange</a>
