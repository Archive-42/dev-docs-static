# GamepadPose.linearAcceleration

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `linearAcceleration` read-only property of the [`GamepadPose`](../gamepadpose) interface returns an array representing the linear acceleration vector of the [`Gamepad`](../gamepad), in meters per second per second.

In other words, the current acceleration of the sensor, along the `x`, `y`, and `z` axes.

## Syntax

    var myGamepadLinAcc = gamepadPoseInstance.linearAcceleration;

### Value

A [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array), or `null` if the gamepad is not able to provide linear acceleration data.

## Examples

TBD

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/gamepad/extensions.html#dom-gamepadpose-linearacceleration">Gamepad Extensions<br />
<span class="small">The definition of 'linearAcceleration' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`linearAcceleration`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GamepadPose/linearAcceleration" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GamepadPose/linearAcceleration</a>
