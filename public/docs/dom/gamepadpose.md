GamepadPose
===========

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `GamepadPose` interface of the [Gamepad API](gamepad_api) represents the pose of a [WebVR](webvr_api) controller at a given timestamp (which includes orientation, position, velocity, and acceleration information.)

This interface is accessible through the [`Gamepad.pose`](gamepad/pose) property.

Properties
----------

 [`GamepadPose.hasOrientation`](gamepadpose/hasorientation) <span class="badge inline readonly">Read only </span>   
Returns a boolean indicating whether the gamepad is capable of returning orientation information (`true`) or not (`false`).

 [`GamepadPose.hasPosition`](gamepadpose/hasposition) <span class="badge inline readonly">Read only </span>   
Returns a boolean indicating whether the gamepad is capable of returning position information (`true`) or not (`false`).

 [`GamepadPose.position`](gamepadpose/position) <span class="badge inline readonly">Read only </span>   
Returns the position of the [`Gamepad`](gamepad) as a 3D vector.

 [`GamepadPose.linearVelocity`](gamepadpose/linearvelocity) <span class="badge inline readonly">Read only </span>   
Returns the linear velocity of the [`Gamepad`](gamepad), in meters per second.

 [`GamepadPose.linearAcceleration`](gamepadpose/linearacceleration) <span class="badge inline readonly">Read only </span>   
Returns the linear acceleration of the [`Gamepad`](gamepad), in meters per second per second.

 [`GamepadPose.orientation`](gamepadpose/orientation) <span class="badge inline readonly">Read only </span>   
Returns the orientation of the [`Gamepad`](gamepad), as a quarternion value.

 [`GamepadPose.angularVelocity`](gamepadpose/angularvelocity) <span class="badge inline readonly">Read only </span>   
Returns the angular velocity of the [`Gamepad`](gamepad), in radians per second.

 [`GamepadPose.angularAcceleration`](gamepadpose/angularacceleration) <span class="badge inline readonly">Read only </span>   
Returns the angular acceleration of the [`Gamepad`](gamepad), in meters per second per second.

Examples
--------

TBD.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/gamepad/extensions.html#gamepadpose-interface">Gamepad Extensions<br />
<span class="small">The definition of 'GamepadPose' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition</td></tr></tbody></table>

Browser compatibility
---------------------

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

`GamepadPose`

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

`angularAcceleration`

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

`angularVelocity`

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

`hasOrientation`

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

`hasPosition`

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

`linearVelocity`

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

See also
--------

-   [WebVR API](webvr_api)
-   [Gamepad API](gamepad_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GamepadPose" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GamepadPose</a>
