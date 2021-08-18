XRFrame.getPose()
=================

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The [`XRFrame`](../xrframe) method `getPose()` returns the relative position and orientation—the pose—of one [`XRSpace`](../xrspace) to that of another space. With this, you can observe the motion of objects relative to each other and to fixed locations throughout the scene.

For example, to get the position of a controller relative to the viewer's head, you would compare the controller's [`gripSpace`](../xrinputsource/gripspace) to the [`XRReferenceSpace`](../xrreferencespace) of type `viewer`.

Syntax
------

    var xrPose = xrFrame.getPose(space, baseSpace);

### Parameters

`space`  
An [`XRSpace`](../xrspace) specifying the space for which to obtain an [`XRPose`](../xrpose) describing the item's position and orientation.

`baseSpace`  
An [`XRSpace`](../xrspace) to use as the base or origin for the purposes of computing the relative position and orientation.

### Return value

An [`XRPose`](../xrpose) object specifying the position and orientation, relative to the [`XRSpace`](../xrspace) indicated by `baseSpace`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrframe-getpose">WebXR Device API<br />
<span class="small">The definition of 'XRFrame.getPose()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getPose`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRFrame/getPose" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRFrame/getPose</a>
