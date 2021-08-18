# DeviceOrientationEvent.absolute

Indicates whether or not the device is providing orientation data absolutely (that is, in reference to the Earth's coordinate frame) or using some arbitrary frame determined by the device. See [Orientation and motion data explained](https://developer.mozilla.org/en-US/docs/Web/Events/Orientation_and_motion_data_explained) for details.

## Syntax

    var absolute = instanceOfDeviceOrientationEvent.absolute;

On return, _`absolute`_ is `true` if the orientation data in `instanceOfDeviceOrientationEvent` is provided as the difference between the Earth's coordinate frame and the device's coordinate frame, or `false` if the orientation data is being provided in reference to some arbitrary, device-determined coordinate frame.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/deviceorientation/">DeviceOrientation Event Specification</a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial specification.</td></tr></tbody></table>

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

`absolute`

7

12

6

No

Yes

?

≤37

Yes

6

Yes

4.2

Yes

## See also

- [`DeviceOrientationEvent`](../deviceorientationevent)
- [Detecting device orientation](https://developer.mozilla.org/en-US/docs/Web/Events/Detecting_device_orientation)
- [Orientation and motion data explained](https://developer.mozilla.org/en-US/docs/Web/Events/Orientation_and_motion_data_explained)
- [`window.ondeviceorientation`](../window/ondeviceorientation)
- `deviceorientation`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DeviceOrientationEvent/absolute" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DeviceOrientationEvent/absolute</a>
