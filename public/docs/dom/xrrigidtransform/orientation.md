XRRigidTransform.orientation
============================

The read-only [`XRRigidTransform`](../xrrigidtransform) property `orientation` is a [`DOMPointReadOnly`](../dompointreadonly) containing a normalized [quaternion](https://developer.mozilla.org/en-US/docs/Glossary/Quaternion) (also called a **unit quaternion** or **[versor](https://en.wikipedia.org/wiki/Versor)**) specifying the rotational component of the transform represented by the object. If you specify a quaternion whose length is not exactly 1.0 meters, it will be normalized for you.

Syntax
------

    let orientation = xrRigidTransform.orientation;

### Value

A [`DOMPointReadOnly`](../dompointreadonly) object which contains a unit quaternion providing the orientation component of the transform. As a unit quaternion, the length of the returned quaternion is always 1.0 meters.

Examples
--------

To create a reference space which is oriented to look straight up, positioned 2 meters off of ground level:

    xrReferenceSpace = refSpace.getOffsetReferenceSpace(
      new XRRigidTransform({y: -2}, {x: 0.0, y: 1.0, z: 0.0, w: 1.0});
    );

The unit quaternion specified here is \[0.0, 1.0, 0.0, 1.0\] to indicate that the object should be facing directly along the *y* axis.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrrigidtransform-orientation">WebXR Device API<br />
<span class="small">The definition of 'XRRigidTransform.orientation' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`orientation`

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

See also
--------

-   [Movement, orientation, and motion](../webxr_device_api/movement_and_motion)
-   [Unit quaternions](https://en.wikipedia.org/wiki/Versor)
-   [Quaternions and spatial rotation](https://en.wikipedia.org/wiki/Quaternions_and_spatial_rotation)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRRigidTransform/orientation" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRRigidTransform/orientation</a>
