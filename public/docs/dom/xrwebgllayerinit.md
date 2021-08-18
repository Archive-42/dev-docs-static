XRWebGLLayerInit
================

The [WebXR Device API](webxr_device_api)'s `XRWebGLLayerInit` dictionary is used to provide configuration options when creating a new [`XRWebGLLayer`](xrwebgllayer) object with the [`XRWebGLLayer()`](xrwebgllayer/xrwebgllayer) constructor. The constructor's optional `layerInit` parameter takes an object which must conform to this dictionary.

Properties
----------

 [`alpha`](xrwebgllayerinit/alpha) <span class="badge inline optional">Optional</span>   
The frame buffer's color buffer will be established with an alpha channel if the `alpha` Boolean property is `true`. Otherwise, the color buffer will not have an alpha channel. The default value is `true`.

 [`antialias`](xrwebgllayerinit/antialias) <span class="badge inline optional">Optional</span>   
A Boolean value which is `true` if anti-aliasing is to be used when rendering in the context; otherwise `false`. The browser selects the anti-aliasing method to use; there is no support for requesting a specific mode yet. The default value is `true`.

 [`depth`](xrwebgllayerinit/depth) <span class="badge inline optional">Optional</span>   
A Boolean value which, if `true`, requests that the new layer have a depth buffer; otherwise, no depth layer is allocated. The default is `true`.

 [`framebufferScaleFactor`](xrwebgllayerinit/framebufferscalefactor) <span class="badge inline optional">Optional</span>   
A floating-point value which is used to scale the image during compositing, with a value of 1.0 represents the default pixel size for the frame buffer. The static [`XRWebGLLayer`](xrwebgllayer) function [`XRWebGLLayer.getNativeFramebufferScaleFactor()`](xrwebgllayer/getnativeframebufferscalefactor) returns the scale that would result in a 1:1 pixel ratio, thereby ensuring that the rendering is occurring at the device's native resolution. The default is 1.0.

 [`ignoreDepthValues`](xrwebgllayerinit/ignoredepthvalues) <span class="badge inline optional">Optional</span>   
A Boolean value which indicates whether or not to ignore the contents of the depth buffer while compositing the scene. The default is `false`.

 [`stencil`](xrwebgllayerinit/stencil) <span class="badge inline optional">Optional</span>   
A Boolean value which, if `true`, requests that the new layer include a stencil buffer. Otherwise, no stencil buffer is allocated. The default is `false`.

Examples
--------

Given an [`XRSession`](xrsession), `xrSession`, and a WebGL rendering context, `gl`, this snippet sets the rendering layer for the session, specifying the `ignoreDepthValues` option, indicating that the depth buffer should not be used (or should not exist at all), and that the only source for distance information of any given point is its position relative to the viewer.

    const layerOptions = {
      ignoreDepthValues: true
    };

    xrSession.updateRenderState({
      baseLayer: new XRWebGLLayer(xrSession, gl, layerOptions);
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dictdef-xrwebgllayerinit">WebXR Device API<br />
<span class="small">The definition of 'XRWebGLLayerInit' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`XRWebGLLayerInit`

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

`alpha`

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

`antialias`

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

`depth`

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

`ignoreDepthValues`

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

-   [WebXR Device API](webxr_device_api)
-   [Getting started with WebGL](webgl_api/tutorial/getting_started_with_webgl)
-   [`WebGLRenderingContext`](webglrenderingcontext) and [`WebGL2RenderingContext`](webgl2renderingcontext)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRWebGLLayerInit" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRWebGLLayerInit</a>
