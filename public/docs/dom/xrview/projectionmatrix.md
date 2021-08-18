XRView.projectionMatrix
=======================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Draft**

This page is not complete.

The [`XRView`](../xrview) interface's read-only `projectionMatrix` property specifies the projection matrix to apply to the underlying view. This should be used to integrate perspective to everything in the scene, in order to ensure the result is consistent with what the eye expects to see.

**Important:** Failure to apply proper perspective, or inconsistencies in perspective, may result in possibly serious user discomfort or distress.

Syntax
------

    let projectionMatrix = xrView.projectionMatrix;

### Value

A [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) object representing the projection matrix for the view. The projection matrix for each eye's view is used to ensure that the correct area of the scene is presented to each eye in order to create a believable 3D scene without introducing discomfort for the user.

Examples
--------

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrview-projectionmatrix">WebXR Device API<br />
<span class="small">The definition of 'XRView.projectionMatrix' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`projectionMatrix`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRView/projectionMatrix" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRView/projectionMatrix</a>
