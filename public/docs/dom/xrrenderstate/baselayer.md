XRRenderState.baseLayer
=======================

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The read-only `baseLayer` property of the [`XRRenderState`](../xrrenderstate) interface returns the [`XRWebGLLayer`](../xrwebgllayer) instance that is the source of bitmap images and a description of how the image is to be rendered in the device.

This property is read-only; however, you can indirectly change its value using [`XRSession.updateRenderState`](../xrsession/updaterenderstate).

Syntax
------

    var xrWebGLLayer = xrRenderState.baseLayer;

### Value

A [`XRWebGLLayer`](../xrwebgllayer) object which is used as the source of the world's contents when rendering each frame of the scene.

See the examples below to see how to use [`updateRenderState()`](../xrsession/updaterenderstate) to set the current `XRWebGLLayer` used for rendering the scene.

Examples
--------

You can set the `XRWebGLLayer` used for rendering by calling [`updateRenderState()`](../xrsession/updaterenderstate), like this:

    let canvas = document.querySelector("canvas");
    gl = canvas.getContext("webgl", { xrCompatible: true });
    setNewWebGLLayer();

    function setNewWebGLLayer(gl) {
      if (!gl) {
        /* WebGL not available */
        return;
      }

      xrSession.updateRenderState({
        baseLayer: new XRWebGLLayer(xrSession, gl);
      });
    };

Here, the canvas obtained in the first line is the canvas into which WebGL is going to draw. That context is passed into [`new   XRWebGLLayer()`](../xrwebgllayer/xrwebgllayer) to create an `XRWebGLLayer` which uses the contents of the WebGL context `gl` as the source of the world's image during presentation.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrrenderstate-baselayer">WebXR Device API<br />
<span class="small">The definition of 'XRRenderState.baseLayer' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`baseLayer`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRRenderState/baseLayer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRRenderState/baseLayer</a>
