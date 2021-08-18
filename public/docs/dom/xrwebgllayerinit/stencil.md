XRWebGLLayerInit.stencil
========================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

When using the [`XRWebGLLayer()`](../xrwebgllayer/xrwebgllayer) constructor to create a new WebGL rendering layer for WebXR, providing as the `layerInit` parameter an object whose `stencil` property is `false` requests that the new layer be created without a stencil buffer.

The **stencil buffer** is an optional buffer which, just like the depth buffer, contains one entry for every pixel in the frame buffer. Also just like the depth buffer, the value of an enter in the stencil buffer directly affects how (or if) the corresponding pixel is drawn during rendering. You can store values into each entry in the stencil bufer, then specify an operation that determines which stencil buffer values correspond to pixels which should be drawn to the screen during each frame.

Syntax
------

    let layerInit = {
      stencil: false
    };
    let glLayer = new XRWebGLLayer(xrSession, gl, layerInit);

    let glLayer = new XRWebGLLayer(xrSession, gl, { stencil: false });

### Value

A Boolean which can be set to `false` to specify that the new WebGL layer should not include a stencil buffer. The default value is `true`.

Example
-------

In this example, a new [`XRWebGLLayer`](../xrwebgllayer) is created for a WebXR session, `xrSession`, without a stencil buffer.

    xrSession.updateRenderState({
      baseLayer: new XRWebGLLayer(xrSession, gl, {
         stencil: false
      });
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrwebgllayerinit-stencil">WebXR Device API<br />
<span class="small">The definition of 'XRWebGLLayerInit.stencil' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`stencil`

79

79

No

No

No

No

79

79

No

No

No

11.2

See also
--------

-   [WebXR Device API](../webxr_device_api)
-   [Getting started with WebGL](../webgl_api/tutorial/getting_started_with_webgl)
-   WebGL stenciling methods include: `stencilOp()`, `clearStencil()`, `stencilFunc()`, `stencilMask()`, `stencilMaskSeparate()`, `stencilFuncSeparate()`, `stencilOpSeparate()`,

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRWebGLLayerInit/stencil" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRWebGLLayerInit/stencil</a>
