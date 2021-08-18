XRPose.emulatedPosition
=======================

**Draft**

This page is not complete.

The `emulatedPosition` read-only attribute of the [`XRPose`](../xrpose) interface is a Boolean value indicating whether or not both the [`position`](../xrrigidtransform/position) component of the pose's [`transform`](transform) is directly taken from the XR device, or it's simulated or computed based on other sources.

Syntax
------

    let emulated = xrPose.emulatedPosition;

### Value

A Boolean which is `true` if the pose's position is computed based on estimates or is derived from sources other than direct sensor data. If the position is precisely gbased on direct sensor inputs, the value is `false`.

Usage notes
-----------

There are two basic categories of XR tracking systems. A basic XR headset provides three degrees of freedom (3DoF), tracking the pitch, yaw, and roll of the user's head. No information is available about movement forward, backward, or to the sides. Any such data is taken from other sources, such as keyboard or mouse inputs or game controllers. As such, the position is considered to be emulated, so the `emulatedPosition` property is `true`.

Contrariwise, XR devices which can also track movement forward and backward as well as laterally—six degree of freedom (6DoF) devices—don't require any information from other sources to determine the user's position, so the value of `emulatedPosition` is `false`.

The same notion applies not just to the user's head, but to any object. A hand controller that can directly report its position would have a value of `false` for this property as well. If its position is computed as an offset from another object (such as by basing it off the model representing the user's body), then this value is `true`.

This information is important because devices whose position is emulated are prone to their offset drifting relative to the real world space over time. This is because emulating a position based on accelerometer inputs and models tends to introduce minor errors which accumulate over time.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrpose-emulatedposition">WebXR Device API<br />
<span class="small">The definition of 'XRPose.emulatedPosition' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`emulatedPosition`

79

79

No

No

No

No

No

79

No

No

No

11.2

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRPose/emulatedPosition" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRPose/emulatedPosition</a>
