# DeviceMotionEvent

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `DeviceMotionEvent` provides web developers with information about the speed of changes for the device's position and orientation.

**Warning:** Currently, Firefox and Chrome do not handle the coordinates the same way. Take care about this while using them.

## Constructor

[`DeviceMotionEvent.DeviceMotionEvent()`](devicemotionevent/devicemotionevent) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
Creates a new `DeviceMotionEvent`.

## Properties

[`DeviceMotionEvent.acceleration`](devicemotionevent/acceleration)<span class="badge inline readonly">Read only </span>  
An object giving the acceleration of the device on the three axis X, Y and Z. Acceleration is expressed in [m/s<sup>2</sup>](https://en.wikipedia.org/wiki/Meter_per_second_squared).

[`DeviceMotionEvent.accelerationIncludingGravity`](devicemotionevent/accelerationincludinggravity)<span class="badge inline readonly">Read only </span>  
An object giving the acceleration of the device on the three axis X, Y and Z with the effect of gravity. Acceleration is expressed in [m/s<sup>2</sup>](https://en.wikipedia.org/wiki/Meter_per_second_squared).

[`DeviceMotionEvent.rotationRate`](devicemotionevent/rotationrate)<span class="badge inline readonly">Read only </span>  
An object giving the rate of change of the device's orientation on the three orientation axis alpha, beta and gamma. Rotation rate is expressed in degrees per seconds.

[`DeviceMotionEvent.interval`](devicemotionevent/interval)<span class="badge inline readonly">Read only </span>  
A number representing the interval of time, in milliseconds, at which data is obtained from the device.

## Example

    window.addEventListener('devicemotion', function(event) {
      console.log(event.acceleration.x + ' m/s2');
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/deviceorientation/#devicemotionevent">DeviceOrientation Event Specification<br />
<span class="small">The definition of 'DeviceMotionEvent' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

11

12

6

No

15

5

≤37

18

6

14

4.2

1.0

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

`interval`

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

- `deviceorientation`
- [`DeviceOrientationEvent`](deviceorientationevent)
- `devicemotion`
- [Detecting device orientation](https://developer.mozilla.org/en-US/docs/Web/Events/Detecting_device_orientation)
- [Orientation and motion data explained](https://developer.mozilla.org/en-US/docs/Web/Events/Orientation_and_motion_data_explained)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DeviceMotionEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DeviceMotionEvent</a>
