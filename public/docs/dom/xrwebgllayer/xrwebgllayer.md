XRWebGLLayer()
==============

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The [WebXR Device API](../webxr_device_api) `XRWebGLLayer()` constructor creates and returns a new [`XRWebGLLayer`](../xrwebgllayer) object, providing the linkage between the WebXR device and the WebGL graphics layer used to render the 3D scene.

Syntax
------

    let glLayer = new XRWebGLLayer(session, context, layerInit);

### Parameters

`session`  
An [`XRSession`](../xrsession) object specifying the WebXR session which will be rendered using the WebGL context.

`context`  
A [`WebGLRenderingContext`](../webglrenderingcontext) or [`WebGL2RenderingContext`](../webgl2renderingcontext) identifying the WebGL drawing context to use for rendering the scene for the specified WebXR session.

 `layerInit` <span class="badge inline optional">Optional</span>   
An object conforming to the [`XRWebGLLayerInit`](../xrwebgllayerinit) dictionary, providing configuration options for the new `XRWebGLLayer`. The options available are:

 [`alpha`](../xrwebgllayerinit/alpha) <span class="badge inline optional">Optional</span>   
The frame buffer's color buffer will be established with an alpha channel if the `alpha` Boolean property is `true`. Otherwise, the color buffer will not have an alpha channel. The default value is `true`.

 [`antialias`](../xrwebgllayerinit/antialias) <span class="badge inline optional">Optional</span>   
A Boolean value which is `true` if anti-aliasing is to be used when rendering in the context; otherwise `false`. The browser selects the anti-aliasing method to use; there is no support for requesting a specific mode yet. The default value is `true`.

 [`depth`](../xrwebgllayerinit/depth) <span class="badge inline optional">Optional</span>   
A Boolean value which, if `true`, requests that the new layer have a depth buffer; otherwise, no depth layer is allocated. The default is `true`.

 [`framebufferScaleFactor`](../xrwebgllayerinit/framebufferscalefactor) <span class="badge inline optional">Optional</span>   
A floating-point value which is used to scale the image during compositing, with a value of 1.0 represents the default pixel size for the frame buffer. The static [`XRWebGLLayer`](../xrwebgllayer) function [`XRWebGLLayer.getNativeFramebufferScaleFactor()`](getnativeframebufferscalefactor) returns the scale that would result in a 1:1 pixel ratio, thereby ensuring that the rendering is occurring at the device's native resolution. The default is 1.0.

 [`ignoreDepthValues`](../xrwebgllayerinit/ignoredepthvalues) <span class="badge inline optional">Optional</span>   
A Boolean value which indicates whether or not to ignore the contents of the depth buffer while compositing the scene. The default is `false`.

 [`stencil`](../xrwebgllayerinit/stencil) <span class="badge inline optional">Optional</span>   
A Boolean value which, if `true`, requests that the new layer include a stencil buffer. Otherwise, no stencil buffer is allocated. The default is `false`.

### Return value

A newly-created [`XRWebGLLayer`](../xrwebgllayer) which links the specified [`XRSession`](../xrsession) to the WebGL context given by `context`, which will be used as the renderer for the session. Any options specified in `layerInit` are used to tailor the rendering system's configuration.

### Exceptions

`InvalidStateError`  
The new `XRWebGLLayer` could not be created due to one of a number of possible state errors:

-   The [`XRSession`](../xrsession) specified by `session` has already been stopped.
-   The specified WebGL context, `context`, [has been lost](../webglrenderingcontext/iscontextlost#usage_notes) for any reason, such as a GPU switch or reset.
-   The specified `session` is immersive but the `context` is not WebXR compatible.

`OperationError`  
The resources (including memory buffers) needed for the layer to operate could not be allocated.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrwebgllayer-xrwebgllayer">WebXR Device API<br />
<span class="small">The definition of 'XRWebGLLayer()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`XRWebGLLayer`

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

See also
--------

-   [WebXR Device API](../webxr_device_api)
-   [Getting started with WebGL](../webgl_api/tutorial/getting_started_with_webgl)
-   [Handling lost context in WebGL](https://www.khronos.org/webgl/wiki/HandlingContextLost): Khronos WebGL wiki

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRWebGLLayer/XRWebGLLayer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRWebGLLayer/XRWebGLLayer</a>
