XRViewport.y
============

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The read-only [`XRViewport`](../xrviewport) interface's `y` property indicates the offset from the bottom edge of the destination surface (typically a [`XRWebGLLayer`](../xrwebgllayer) to the bottom edge of the viewport within the surface into which WebXR content is to be rendered. The viewport's [`x`](x) property identifies the `x` component of the origin, and its is given by the [`width`](width) and [`height`](height) properties.

Syntax
------

    y = xrViewport.y;

### Value

The offset from the bottom edge of the rendering surface to the bottom edge of the viewport, in pixels.

**Note:** Although other web APIs typically consider the `y` axis to begin at the top and grow larger progressing downward, WebGL reverses this, with `y` growing larger as it goes upward on the screen.

Examples
--------

See the main [`XRViewport`](../xrviewport) page for examples.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrviewport-y">WebXR Device API<br />
<span class="small">The definition of 'XRViewport.y' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`y`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRViewport/y" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRViewport/y</a>
