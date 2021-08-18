XRRenderState.inlineVerticalFieldOfView
=======================================

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The read-only `inlineVerticalFieldOfView` property of the [`XRRenderState`](../xrrenderstate) interface returns the default vertical field of view for `"inline"` sessions and `null` for all immersive sessions.

Syntax
------

    var inlineVerticalFieldOfView = xrRenderState.inlineVerticalFieldOfView;

### Value

A [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) for `"inline"` sessions, which represents the default field of view, and `null` for immersive sessions.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrrenderstate-inlineVerticalFieldOfView">WebXR Device API<br />
<span class="small">The definition of 'XRRenderState.inlineVerticalFieldOfView' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`inlineVerticalFieldOfView`

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

12.0

See also
--------

-   [`navigator.xr.requestSession()`](../xrsystem/requestsession)
-   [`navigator.xr.isSessionSupported()`](../xrsystem/issessionsupported)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRRenderState/inlineVerticalFieldOfView" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRRenderState/inlineVerticalFieldOfView</a>
