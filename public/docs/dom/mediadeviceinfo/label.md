# MediaDeviceInfo.label

The `label` readonlyinline property of the [`MediaDeviceInfo`](../mediadeviceinfo) interface returns a [`DOMString`](../domstring), that is a label describing this device (for example "External USB Webcam"). Only available during active `MediaStream` use, or when persistent permissions have been granted.

## Syntax

    var label = MediaDeviceInfo.label;

### Value

A [`DOMString`](../domstring) which describes the media device. For security reasons, the `label` is always an empty string (`""`) if the user has not obtained permission to use at least one media device, either by starting a stream from the microphone or camera, or by persistent permissions being granted.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediadeviceinfo-label">Media Capture and Streams<br />
<span class="small">The definition of 'label' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`label`

55

12

39

No

42

11

55

55

39

42

11

6.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaDeviceInfo/label" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaDeviceInfo/label</a>
