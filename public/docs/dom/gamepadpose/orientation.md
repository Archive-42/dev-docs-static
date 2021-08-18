# GamepadPose.orientation

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `orientation` read-only property of the [`GamepadPose`](../gamepadpose) interface returns the orientation of the [`Gamepad`](../gamepad), as a quarternion value.

The value is a [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array), made up of the following values:

- pitch — rotation around the X axis.
- yaw — rotation around the Y axis.
- roll — rotation around the Z axis.
- w — the fourth dimension (usually 1).

The orientation yaw (rotation around the y axis) is relative to the initial yaw of the sensor when it was first read.

## Syntax

    var myGamepadOrientation = gamepadPoseInstance.orientation;

### Value

A [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array), or `null` if the VR sensor is not able to provide orientation data.

## Examples

TBD

**Note**: An orientation of `{ x: 0, y: 0, z: 0, w: 1 }` is considered to be "forward".

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/gamepad/extensions.html#dom-gamepadpose-orientation">Gamepad Extensions<br />
<span class="small">The definition of 'orientation' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`orientation`

No

15-79

55

No

No

No

No

No

55

No

No

No

## See also

- [WebVR API](../webvr_api)
- [Gamepad API](../gamepad_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GamepadPose/orientation" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GamepadPose/orientation</a>
