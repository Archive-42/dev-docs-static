XRWebGLLayer
============

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `XRWebGLLayer` interface of the WebXR Device API provides a linkage between the WebXR device (or simulated XR device, in the case of an inline session) and a WebGL context used to render the scene for display on the device. In particular, it provides access to the WebGL framebuffer and viewport to ease access to the context.

Although `XRWebGLLayer` is currently the only type of framebuffer layer supported by [WebGL](webgl_api), it's entirely possible that future updates to the WebXR specification may allow for other layer types and corresponding image sources.

Constructor
-----------

[`new XRWebGLLayer()`](xrwebgllayer/xrwebgllayer)  
Creates and returns a new `XRWebGLLayer` object for use by the specified [`XRSession`](xrsession), using a particular [`WebGLRenderingContext`](webglrenderingcontext) or [`WebGL2RenderingContext`](webgl2renderingcontext) as the destination context.

Properties
----------

 [`antialias`](xrwebgllayer/antialias) <span class="badge inline readonly">Read only </span>   
A Boolean value indicating whether or not the WebGL context's framebuffer supports anti-aliasing. The specific type of anti-aliasing is determined by the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent).

 [`framebuffer`](xrwebgllayer/framebuffer) <span class="badge inline readonly">Read only </span>   
Returns a [`WebGLFramebuffer`](webglframebuffer) suitable for passing into the [`bindFrameBuffer()`](webglrenderingcontext/bindframebuffer) method.

 [`framebufferWidth`](xrwebgllayer/framebufferwidth) <span class="badge inline readonly">Read only </span>   
Returns the width of the `XRWebGLLayer`'s framebuffer.

 [`framebufferHeight`](xrwebgllayer/framebufferheight) <span class="badge inline readonly">Read only </span>   
Returns the height of the layer's framebuffer.

 [`ignoreDepthValues`](xrwebgllayer/ignoredepthvalues) <span class="badge inline readonly">Read only </span>   
A Boolean which Indicates whether or not the [WebXR compositor](en-us/docs/web/api/webxr_device_api/fundamentals#The_WebXR_compositor) should make use of the contents of the layer's depth buffer while compositing the scene.

Methods
-------

[`getViewport()`](xrwebgllayer/getviewport)  
Returns a new [`XRViewport`](xrviewport) instance representing the position, width, and height to which the [WebGL context's viewport](webglrenderingcontext/viewport) must be set to contain drawing to the area of the framebuffer designated for the specified view's contents. In this way, for example, the rendering of the left eye's point of view and of the right eye's point of view are each placed into the correct parts of the framebuffer.

Static methods
--------------

[`getNativeFramebufferScaleFactor()`](xrwebgllayer/getnativeframebufferscalefactor)  
Returns the scaling factor that can be used to scale the resolution of the recommended WebGL framebuffer resolution to the rendering device's native resolution.

Examples
--------

### Binding the layer to a WebGL context

This snippet, taken from [Drawing a frame](webxr_device_api/movement_and_motion#drawing_a_frame) in [Movement, orientation, and motion: A WebXR example](webxr_device_api/movement_and_motion), shows how the `XRWebGLLayer` is obtained from the [`XRSession`](xrsession) object's rendering state and is then bound as the current rendering WebGL framebuffer by calling the WebGL [`bindFrameBuffer()`](webglrenderingcontext/bindframebuffer) function.

    let glLayer = xrSession.renderState.baseLayer;
    gl.bindFrameBuffer(gl.FRAMEBUFFER, glLayer.framebuffer);

### Rendering every view in a frame

Each time the GPU is ready to render the scene to the XR device, the XR runtime calls the function you specified when you called the [`XRSession`](xrsession) method [`requestAnimationFrame()`](xrsession/requestanimationframe) to ask to render the frame.

That function receives as input an [`XRFrame`](xrframe) which encapsulates the data needed to render the frame. This information includes the pose (an [`XRViewerPose`](xrviewerpose) object) that describes the position and facing direction of the viewer within the scene as well as a list of [`XRView`](xrview) objects, each representing one perspective on the scene. In current WebXR implementations, there will never be more than two entries in this list: one describing the position and viewing angle of the left eye and another doing the same for the right.

    let pose = xrFrame.getViewerPose(xrReferenceSpace);

    if (pose) {
      let glLayer = xrSession.renderState.baseLayer;
      gl.bindFrameBuffer(gl.FRAMEBUFFER, glLayer.Framebffer);

      for (let view of pose.views) {
        let viewport = glLayer.getViewport(view);
        gl.viewport(viewport.x, viewport.y, viewport.width, viewport.height);

        /* Render the view */
      }
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#xrwebgllayer-interface">WebXR Device API<br />
<span class="small">The definition of 'XRWebGLLayer' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`antialias`

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

`framebuffer`

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

`framebufferHeight`

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

`framebufferWidth`

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

`getNativeFramebufferScaleFactor`

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

`getViewport`

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

`ignoreDepthValues`

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

-   [WebXR Device API](webxr_device_api)
-   [Getting started with WebGL](webgl_api/tutorial/getting_started_with_webgl)
-   [`WebGLRenderingContext`](webglrenderingcontext) and [`WebGL2RenderingContext`](webgl2renderingcontext)
-   [Drawing a frame](webxr_device_api/movement_and_motion#drawing_a_frame) in [Movement, orientation, and motion: A WebXR example](webxr_device_api/movement_and_motion)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRWebGLLayer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRWebGLLayer</a>
