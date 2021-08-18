# DeviceOrientationEvent.DeviceOrientationEvent()

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `DeviceOrientationEvent` constructor creates a new [`DeviceOrientationEvent`](../deviceorientationevent).

## Syntax

    var deviceOrientationEvent = new DeviceOrientationEvent(type[, options])

### Parameters

_type_  
Either `"deviceorientation"` or `"deviceorientationabsolute"`. If the later, then `options.absolute` should be true.

_options_ <span class="badge inline optional">Optional</span>  
Options are as follows:

- `alpha`: A number representing the motion of the device around the z axis, express in degrees with values ranging from 0 to 360.
- `beta`: A number representing the motion of the device around the x axis, express in degrees with values ranging from -180 to 180. This represents a front to back motion of the device.
- `gamma`: A number representing the motion of the device around the y axis, express in degrees with values ranging from -90 to 90. This represents a left to right motion of the device.
- `absolute`: A boolean that indicates whether or not the device is providing orientation data absolutely.

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

`DeviceOrientationEvent`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DeviceOrientationEvent/DeviceOrientationEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DeviceOrientationEvent/DeviceOrientationEvent</a>
