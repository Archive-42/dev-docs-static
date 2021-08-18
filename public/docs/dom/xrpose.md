XRPose
======

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Draft**

This page is not complete.

`XRPose` is a [WebXR API](webxr_device_api) interface representing a position and orientation in the 3D space, relative to the [`XRSpace`](xrspace) within which it resides. The `XRSpace`—which is either an [`XRReferenceSpace`](xrreferencespace) or an [`XRBoundedReferenceSpace`](xrboundedreferencespace)—defines the coordinate system used for the pose and, in the case of an [`XRViewerPose`](xrviewerpose), its underlying views.

To obtain the `XRPose` for the `XRSpace` used as the local coordinate system of an object, call [`XRFrame.getPose()`](xrframe/getpose), specifying that local `XRSpace` and the space to which you wish to convert:

    thePose = xrFrame.getPose(localSpace, baseSpace);

The pose for a viewer (or camera) is represented by the [`XRViewerPose`](xrviewerpose) subclass of `XRPose`. This is obtained using [`XRFrame.getViewerPose()`](xrframe/getviewerpose) instead of `getPose()`, specifying a reference space which has been adjusted to position and orient the node to provide the desired viewing position and angle:

    viewerPose = xrFrame.getViewerPose(adjReferenceSpace);

Here, `adjReferenceSpace` is a reference space which has been updated using the base frame of reference for the frame and any adjustments needed to position the viewer based on movement or rotation which is being supplied from a source other than the XR device, such as keyboard or mouse inputs**.**

See the article [Movement, orientation, and motion](webxr_device_api/movement_and_motion) for further details and an example with thorough explanations of what's going on.

Properties
----------

 [`XRPose.transform`](xrpose/transform) <span class="badge inline readonly">Read only </span>   
A [`XRRigidTransform`](xrrigidtransform) which provides the position and orientation of the pose relative to the base [`XRSpace`](xrspace).

 [`XRPose.emulatedPosition`](xrpose/emulatedposition) <span class="badge inline readonly">Read only </span>   
A Boolean value which is `false` if the position and orientation given by [`transform`](xrpose/transform) is obtained directly from a full six degree of freedom (6DoF) XR device (that is, a device which tracks not only the pitch, yaw, and roll of the head but also the forward, backward, and side-to-side motion of the viewer). If any component of the `transform` is computed or created artificially (such as by using mouse or keyboard controls to move through space), this value is instead `true`, indicating that the `transform` is in part emulated in software.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#xrpose-interface">WebXR Device API<br />
<span class="small">The definition of 'XRPose' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`XRPose`

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

`transform`

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

-   [WebXR Device API](webxr_device_api)
-   [`XRFrame.getPose()`](xrframe/getpose)
-   [`XRViewerPose`](xrviewerpose)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRPose" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRPose</a>
