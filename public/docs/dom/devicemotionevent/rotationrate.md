# DeviceMotionEvent.rotationRate

Returns the rate at which the device is rotating around each of its axes in degrees per second.

**Note**: If the hardware isn't capable of providing this information, this property returns `null`.

## Syntax

    var rotationRate = deviceMotionEvent.rotationRate;

## Value

The `rotationRate` property is a read only object describing the rotation rates of the device around each of its axes:

`alpha`  
The rate at which the device is rotating about its Z axis; that is, being twisted about a line perpendicular to the screen.

`beta`  
The rate at which the device is rotating about its X axis; that is, front to back.

`gamma`  
The rate at which the device is rotating about its Y axis; that is, side to side.

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

`rotationRate`

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

## See also

- [`DeviceMotionEvent`](../devicemotionevent)
- `devicemotion`
- [`window.ondevicemotion`](../window/ondevicemotion)
- `deviceorientation`
- [`DeviceOrientationEvent`](../deviceorientationevent)
- [Detecting device orientation](https://developer.mozilla.org/en-US/docs/Web/Events/Detecting_device_orientation)
- [Orientation and motion data explained](https://developer.mozilla.org/en-US/docs/Web/Events/Orientation_and_motion_data_explained)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DeviceMotionEvent/rotationRate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DeviceMotionEvent/rotationRate</a>
