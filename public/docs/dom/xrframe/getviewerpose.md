XRFrame.getViewerPose()
=======================

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `getViewerPose()` method, a member of the [`XRFrame`](../xrframe) interface, returns a [`XRViewerPose`](../xrviewerpose) object which describes the viewer's pose (position and orientation) relative to the specified reference space.

See the [`getPose()`](getpose) method for a way to calculate a pose that represents the difference between two spaces.

Syntax
------

    var xrViewerPose = xrFrame.getViewerPose(referenceSpace);

### Parameters

`referenceSpace`  
An [`XRReferenceSpace`](../xrreferencespace) object specifying the space to use as the reference point or base for the computation of the viewer's current pose.

### Return value

A [`XRViewerPose`](../xrviewerpose) describing the viewer's position and orientation relative to the specified reference space.

### Exceptions

`InvalidStateError`  
A [`DOMException`](../domexception) indicating that `getViewerPose()` was not called within the context of a callback to a session's [`XRSession.requestAnimationFrame()`](../xrsession/requestanimationframe).

Examples
--------

In this callback function for [`requestAnimationFrame()`](../xrsession/requestanimationframe), the [`XRViewerPose`](../xrviewerpose) describing the viewer's viewpoint on the world is obtained by calling `getViewerPose()` on the [`XRFrame`](../xrframe) passed into the callback.

    viewerPose = xrFrame.getViewerPose(xrReferenceSpace);

    if (viewerPose) {
      /* render the pose's views */
    }

To see a complete example, take a look at [Movement, orientation, and motion](../webxr_device_api/movement_and_motion).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrframe-getviewerpose">WebXR Device API<br />
<span class="small">The definition of 'XRFrame.getViewerPose()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getViewerPose`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRFrame/getViewerPose" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRFrame/getViewerPose</a>
