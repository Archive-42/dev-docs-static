# DeviceMotionEvent.DeviceMotionEvent()

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `DeviceMotionEvent` constructor creates a new [`DeviceMotionEvent`](../devicemotionevent).

## Syntax

    var deviceMotionEvent = new DeviceMotionEvent(type[, options])

### Parameters

`type`  
Must be `"devicemotion"`.

`options`<span class="badge inline optional">Optional</span>  
Options are as follows:

- `acceleration`: An object giving the acceleration of the device on the three axis X, Y and Z. Acceleration is expressed in [m/s<sup>2</sup>](https://en.wikipedia.org/wiki/Meter_per_second_squared).
- `accelerationIncludingGravity`: An object giving the acceleration of the device on the three axis X, Y and Z with the effect of gravity. Acceleration is expressed in [m/s<sup>2</sup>](https://en.wikipedia.org/wiki/Meter_per_second_squared).
- `rotationRate`: An object giving the rate of change of the device's orientation on the three orientation axis alpha, beta and gamma. Rotation rate is express in degrees per seconds.
- `interval`: A number representing the interval of time, in milliseconds, at which data is obtained from the device.

## Specifications

_Not part of any specifications._

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

`DeviceMotionEvent`

59

14

?

No

?

?

59

59

?

?

?

7.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DeviceMotionEvent/DeviceMotionEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DeviceMotionEvent/DeviceMotionEvent</a>
