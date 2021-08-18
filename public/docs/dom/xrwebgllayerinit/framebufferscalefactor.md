XRWebGLLayerInit.framebufferScaleFactor
=======================================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The [`XRWebGLLayerInit`](../xrwebgllayerinit) dictionary's `framebufferScaleFactor` property, when specified upon instantiating a new [`XRWebGLLayer`](../xrwebgllayer) using its constructor, [`XRWebGLLayer()`](../xrwebgllayer/xrwebgllayer), specifies the scaling factor to use when determining the size of the frame buffer to use when rendering the scene, relative to the default XR device display resolution.

For example, a value of 1.0 indicates that the frame buffer should be the same resolution as the actual display, while a value of 0.5 indicates that the frame buffer should be half the resolution of the display. A value of 2.0, on the other hand, creates a frame buffer whose resolution is *double* that of the actual display buffer.

There are valid use cases for all of these kinds of scaling. See [Managing rendering quality](../webxr_device_api/performance#managing_rendering_quality) in [WebXR performance guide](../webxr_device_api/performance) for more information.

You can determine the scaling factor that you would need to apply to match the default frame buffer resolution by using the [`XRWebGLLayer.getNativeFramebufferScaleFactor()`](../xrwebgllayer/getnativeframebufferscalefactor) static function.

Syntax
------

    let layerInit = {
      framebufferScaleFactor: scaleFactor
    };
    let glLayer = new XRWebGLLayer(xrSession, gl, layerInit);

    let glLayer = new XRWebGLLayer(xrSession, gl, { framebufferScaleFactor: scaleFactor });

### Value

A floating-point value indicating a multiplier to apply to the default frame buffer resolution in order to determine the resolution of the frame buffer for the [`XRWebGLLayer`](../xrwebgllayer).

Example
-------

In this example, a new [`XRWebGLLayer`](../xrwebgllayer) is created for a WebXR session, `xrSession`, with a frame buffer whose resolution is half that of the default display resolution of the XR device.

    xrSession.updateRenderState({
      baseLayer: new XRWebGLLayer(xrSession, gl, {
         framebufferScaleFactor: 0.5
      });
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrwebgllayerinit-framebufferscalefactor">WebXR Device API<br />
<span class="small">The definition of 'XRWebGLLayerInit.framebufferScaleFactor' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`framebufferScaleFactor`

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
-   [WebXR performance guide](../webxr_device_api/performance)
-   [`XRWebGLLayer.getNativeFramebufferScaleFactor()`](../xrwebgllayer/getnativeframebufferscalefactor)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRWebGLLayerInit/framebufferScaleFactor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRWebGLLayerInit/framebufferScaleFactor</a>
