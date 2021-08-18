# DeviceOrientationEvent

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `DeviceOrientationEvent` provides web developers with information from the physical orientation of the device running the web page.

## Constructor

[`DeviceOrientationEvent.DeviceOrientationEvent()`](deviceorientationevent/deviceorientationevent)  
Creates a new `DeviceOrientationEvent`.

## Properties

[`DeviceOrientationEvent.absolute`](deviceorientationevent/absolute) <span class="badge inline readonly">Read only </span>  
A boolean that indicates whether or not the device is providing orientation data absolutely.

[`DeviceOrientationEvent.alpha`](deviceorientationevent/alpha) <span class="badge inline readonly">Read only </span>  
A number representing the motion of the device around the z axis, express in degrees with values ranging from 0 (inclusive) to 360 (exclusive).

[`DeviceOrientationEvent.beta`](deviceorientationevent/beta) <span class="badge inline readonly">Read only </span>  
A number representing the motion of the device around the x axis, express in degrees with values ranging from -180 (inclusive) to 180 (exclusive). This represents a front to back motion of the device.

[`DeviceOrientationEvent.gamma`](deviceorientationevent/gamma) <span class="badge inline readonly">Read only </span>  
A number representing the motion of the device around the y axis, express in degrees with values ranging from -90 (inclusive) to 90 (exclusive). This represents a left to right motion of the device.

DeviceOrientationEvent.webkitCompassHeading <span class="badge inline readonly">Read only </span>  
A number represents the difference between the motion of the device around the z axis of the world system and the direction of the north, express in degrees with values ranging from 0 to 360.

DeviceOrientationEvent.webkitCompassAccuracy <span class="badge inline readonly">Read only </span>  
The accuracy of the compass means that the deviation is positive or negative. It's usually 10.

## Example

    window.addEventListener('deviceorientation', function(event) {
      console.log(event.alpha + ' : ' + event.beta + ' : ' + event.gamma);
    });

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

`DeviceOrientationEvent`

7

Before version 50, Chrome provided absolute values instead of relative values for this event. Developers still needing absolute values may use the `ondeviceorientationabsolute` event.

12

6

Firefox 3.6, 4, and 5 supported `mozOrientation` instead of the standard DeviceOrientationEvent interface.

No

15

5

≤37

Before version 50, Chrome provided absolute values instead of relative values for this event. Developers still needing absolute values may use the `ondeviceorientationabsolute` event.

18

Before version 50, Chrome provided absolute values instead of relative values for this event. Developers still needing absolute values may use the `ondeviceorientationabsolute` event.

6

Firefox 3.6, 4, and 5 supported `mozOrientation` instead of the standard DeviceOrientationEvent interface.

14

4.2

1.0

Before Samsung Internet 5.0, Samsung Internet provided absolute values instead of relative values for this event. Developers still needing absolute values may use the `ondeviceorientationabsolute` event.

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

`alpha`

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

`beta`

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

`gamma`

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

- `deviceorientation`
- [`DeviceMotionEvent`](devicemotionevent)
- `devicemotion`
- [Detecting device orientation](https://developer.mozilla.org/en-US/docs/Web/Events/Detecting_device_orientation)
- [Orientation and motion data explained](https://developer.mozilla.org/en-US/docs/Web/Events/Orientation_and_motion_data_explained)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DeviceOrientationEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DeviceOrientationEvent</a>
