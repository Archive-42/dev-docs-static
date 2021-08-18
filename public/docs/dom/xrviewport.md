XRViewport
==========

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The WebXR Device API's `XRViewport` interface provides properties used to describe the size and position of the current viewport within the [`XRWebGLLayer`](xrwebgllayer) being used to render the 3D scene.

Properties
----------

 [`height`](xrviewport/height) <span class="badge inline readonly">Read only </span>   
The height, in pixels, of the viewport.

 [`width`](xrviewport/width) <span class="badge inline readonly">Read only </span>   
The width, in pixels, of the viewport.

 [`x`](xrviewport/x) <span class="badge inline readonly">Read only </span>   
The offset from the origin of the destination graphics surface (typically a [`XRWebGLLayer`](xrwebgllayer)) to the left edge of the viewport, in pixels.

 [`y`](xrviewport/y) <span class="badge inline readonly">Read only </span>   
The offset from the origin of the viewport to the bottom edge of the viewport; WebGL's coordinate system places (0, 0) at the bottom left corner of the surface.

Usage notes
-----------

Currently, the only type of surface available is the [`XRWebGLLayer`](xrwebgllayer). The precise orientation of the coordinate system may vary with other surface types, but in WebGL, the origin (0, 0) is located at the bottom-left corner of the surface. Thus the values specified in an `XRViewport` define a rectangle whose bottom-left corner is at (`x`, `y`) and which extends `width` pixels toward the left and `height` pixels upward.

These values may be passed directly into the [`WebGLRenderingContext.viewport()`](webglrenderingcontext/viewport) method:

    let xrViewport = xrWebGLLayer.getViewport(xrView);
    gl.viewport(xrViewport.x, xrViewport.y, xrViewport.width, xrViewport.height);

Example
-------

This example sets up an animation frame callback using [`requestAnimationFrame()`](xrsession/requestanimationframe). After initial setup, it iterates over each of the views within the viewer's pose, configuring the viewport as dictated by the [`XRWebGLLayer`](xrwebgllayer).

    xrSession.requestAnimationFrame((time, xrFrame) => {
      let viewerPose = xrFrame.getViewerPose(xrReferenceSpace);

      gl.bindFramebuffer(xrWebGLLayer.framebuffer);

      for (xrView of viewerPose.views) {
        let xrViewport = xrWebGLLayer.getViewport(xrView);
        gl.viewport(xrViewport.x, xrViewport.y, xrViewport.width, xrViewport.height);

       // Now we can use WebGL to draw into a viewport matching
       // the viewer's needs
      }
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#xrviewport-interface">WebXR Device API<br />
<span class="small">The definition of 'XRViewport' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`XRViewport`

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

`height`

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

`width`

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

`x`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRViewport" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRViewport</a>
