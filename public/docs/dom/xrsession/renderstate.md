XRSession.renderState
=====================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The *read-only* `renderState` property of an [`XRSession`](../xrsession) object indicates the returns a [`XRRenderState`](../xrrenderstate) object describing how the user's environment which should be rendered. The information provided covers the minimum and maximum distance at which to render objects, the vertical field of view to use when rendering the in the `inline` session mode, and the [`XRWebGLLayer`](../xrwebgllayer) to render into for inline composition.

While this property is read only, you can call the [`XRSession`](../xrsession) method [`updateRenderState()`](updaterenderstate) to make changes.

Syntax
------

    var xrRenderState = XRSession.renderState;

### Value

An [`XRRenderState`](../xrrenderstate) object describing how to render the scene.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrsession-renderstate">WebXR Device API<br />
<span class="small">The definition of 'XRSession.renderState' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`renderState`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRSession/renderState" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRSession/renderState</a>
