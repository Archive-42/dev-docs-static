# DeviceMotionEvent.acceleration

The `acceleration` property returns the amount of acceleration recorded by the device, in [meters per second squared (m/s<sup>2</sup>)](https://en.wikipedia.org/wiki/Meter_per_second_squared).

**Note:** If the hardware doesn't know how to remove gravity from the acceleration data, this value may not be present in the [`DeviceMotionEvent`](../devicemotionevent). In this situation, you'll need to use [`DeviceMotionEvent.accelerationIncludingGravity`](accelerationincludinggravity) instead.

## Syntax

    var acceleration = deviceMotionEvent.acceleration;

## Value

The `acceleration` property is an object providing information about acceleration on three axis. Each axis is represented with its own property:

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

`acceleration`

Yes

12

6

No

Yes

?

Yes

Yes

6

?

4.2

Yes

## See also

- [`DeviceMotionEvent.accelerationIncludingGravity`](accelerationincludinggravity)
- `devicemotion`
- [`window.ondevicemotion`](../window/ondevicemotion)
- `deviceorientation`
- [`DeviceOrientationEvent`](../deviceorientationevent)
- [Detecting device orientation](https://developer.mozilla.org/en-US/docs/Web/Events/Detecting_device_orientation)
- [Orientation and motion data explained](https://developer.mozilla.org/en-US/docs/Web/Events/Orientation_and_motion_data_explained)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DeviceMotionEvent/acceleration" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DeviceMotionEvent/acceleration</a>
