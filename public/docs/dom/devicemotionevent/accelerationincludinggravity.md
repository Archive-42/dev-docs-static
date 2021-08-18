# DeviceMotionEvent.accelerationIncludingGravity

The `accelerationIncludingGravity` property returns the amount of acceleration recorded by the device, in [meters per second squared (m/s<sup>2</sup>)](https://en.wikipedia.org/wiki/Meter_per_second_squared). Unlike [`DeviceMotionEvent.acceleration`](acceleration) which compensates for the influence of gravity, its value is the sum of the acceleration of the device as induced by the user and the acceleration caused by gravity.

This value is not typically as useful as [`DeviceMotionEvent.acceleration`](acceleration), but may be the only value available on devices that aren't able of removing gravity from the acceleration data, such as on devices that don't have a gyroscope.

## Syntax

    var acceleration = deviceMotionEvent.accelerationIncludingGravity;

## Value

The `accelerationIncludingGravity` property is an object providing information about acceleration on three axis. Each axis is represented with its own property:

`x`  
Represents the acceleration upon the x axis which is the west to east axis

`y`  
Represents the acceleration upon the y axis which is the south to north axis

`z`  
Represents the acceleration upon the z axis which is the down to up axis

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/deviceorientation/">DeviceOrientation Event Specification</a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`accelerationIncludingGravity`

Yes

12

6

No

Yes

?

Yes

Yes

6

Yes

4.2

Yes

The compatibility table on this page is generated from structured data. If you'd like to contribute to the data, please check out <https://github.com/mdn/browser-compat-data> and send us a pull request.

## See also

- [`DeviceMotionEvent.acceleration`](acceleration)
- `devicemotion`
- [`window.ondevicemotion`](../window/ondevicemotion)
- `deviceorientation`
- [`DeviceOrientationEvent`](../deviceorientationevent)
- [Detecting device orientation](https://developer.mozilla.org/en-US/docs/Web/Events/Detecting_device_orientation)
- [Orientation and motion data explained](https://developer.mozilla.org/en-US/docs/Web/Events/Orientation_and_motion_data_explained)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DeviceMotionEvent/accelerationIncludingGravity" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DeviceMotionEvent/accelerationIncludingGravity</a>
