# GamepadPose.position

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `position` read-only property of the [`GamepadPose`](../gamepadpose) interface returns the position of the [`Gamepad`](../gamepad) as a 3D vector.

The coordinate system is as follows:

- Positive X is to the user’s right.
- Positive Y is up.
- Positive Z is behind the user.

Positions are measured in meters from an origin point — this point is the position the sensor was first read at.

## Syntax

    var myGamepadPosition = gamepadPoseInstance.position;

### Value

A [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array), or `null` if the gamepad is not able to provide position data.

**Note**: User agents may provide emulated position values through certain techniques; when doing so they should still report [`GamepadPose.hasPosition`](hasposition) as false.

## Examples

TBD

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/gamepad/extensions.html#dom-gamepadpose-position">Gamepad Extensions<br />
<span class="small">The definition of 'position' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`position`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GamepadPose/position" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GamepadPose/position</a>
