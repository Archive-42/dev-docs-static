XRRigidTransform
================

The `XRRigidTransform` is a [WebXR API](webxr_device_api) interface that represents the 3D geometric transform described by a position and orientation.

`XRRigidTransform` is used to specify transforms throughout the WebXR APIs, including:

-   The offset and orientation relative to the parent reference space to use when creating a new reference space with [`getOffsetReferenceSpace()`](xrreferencespace/getoffsetreferencespace).
-   The [`transform`](xrview/transform) of an [`XRView`](xrview).
-   The [`transform`](xrpose/transform) of an [`XRPose`](xrpose).
-   The [`XRReferenceSpaceEvent`](xrreferencespaceevent) event's [`transform`](xrreferencespaceevent/transform) property, as found in the [`reset`](xrreferencespace/reset_event) event received by an [`XRReferenceSpace`](xrreferencespace).

Using `XRRigidTransform` in these places rather than bare arrays that provide the matrix data has an advantage. It automatically computes the inverse of the transform and even caches it making subsequent requests significantly faster.

Constructor
-----------

[`new XRRigidTransform()`](xrrigidtransform/xrrigidtransform)  
Creates a new `XRRigidTransform` object which represents a transform that applies a specified position and/or orientation.

Properties
----------

 [`XRRigidTransform.position`](xrrigidtransform/position) <span class="badge inline readonly">Read only </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
A [`DOMPointReadOnly`](dompointreadonly) specifying a 3-dimensional point, expressed in meters, describing the translation component of the transform. The [`w`](dompointreadonly/w) property is always `1.0`.

 [`XRRigidTransform.orientation`](xrrigidtransform/orientation) <span class="badge inline readonly">Read only </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
A [`DOMPointReadOnly`](dompointreadonly) which contains a unit quaternion describing the rotational component of the transform. As a unit quaternion, its length is always normalized to `1.0`.

 [`XRRigidTransform.matrix`](xrrigidtransform/matrix) <span class="badge inline readonly">Read only </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Returns the transform matrix in the form of a 16-member [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array). See the section [Matrix format](xrrigidtransform/matrix#matrix_format) for how the array is used to represent a matrix.

 [`XRRigidTransform.inverse`](xrrigidtransform/inverse) <span class="badge inline readonly">Read only </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Returns a `XRRigidTransform` which is the inverse of this transform. That is, if applied to an object that had been previously transformed by the original transform, it will undo the transform and return the original object.

Usage notes
-----------

When an `XRRigidTransform` is interpreted, the orientation is always applied to the affected object before the position is applied.

Example
-------

This code snippet creates an `XRRigidTransform` to specify the offset and orientation in relation to the current reference space to use when creating a new reference space. It then requests the first animation frame callback by calling the session's [`requestAnimationFrame()`](xrsession/requestanimationframe) method.

    xrSession.requestReferenceSpace(refSpaceType)
    .then((refSpace) => {
      xrReferenceSpace = refSpace;
      xrReferenceSpace = xrReferenceSpace.getOffsetReferenceSpace(
            new XRRigidTransform(viewerStartPosition, cubeOrientation));
      animationFrameRequestID = xrSession.requestAnimationFrame(drawFrame);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#xrrigidtransform-interface">WebXR Device API<br />
<span class="small">The definition of 'XRRigidTransform' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`XRRigidTransform`

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

`XRRigidTransform`

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

`inverse`

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

`matrix`

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

`position`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRRigidTransform" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRRigidTransform</a>
