XRWebGLLayer.getViewport()
==========================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The [`XRWebGLLayer`](../xrwebgllayer) interface's `getViewport()` method returns the [`XRViewport`](../xrviewport) that should be used to render the specified [`XRView`](../xrview) into the WebGL layer. For WebXR devices which use a single framebuffer for both the left and right eyes, the returned viewport represents the region of the framebuffer into which the scene should be rendered for the eye represented by the view.

Syntax
------

    let viewport = xrWebGLLayer.getViewport(view);

### Parameters

`view`  
An [`XRView`](../xrview) object indicating the view for which the viewport is to be returned.

### Return value

A [`XRViewport`](../xrviewport) object representing the viewport which will restrict drawing to the portion of the layer corresponding to the specified `view`.

### Exceptions

`InvalidStateError`  
Either the specified `view` is not in an active [`XRFrame`](../xrframe) or that `XRFrame` and the [`XRWebGLLayer`](../xrwebgllayer) are not part of the same [WebXR session](../xrsession).

Example
-------

This example demonstrates in part what the callback for the [`requestAnimationFrame()`](../xrsession/requestanimationframe) function might look like, using `getViewport()` to get the viewport so that drawing can be constrained to the area set aside for the eye whose viewpoint is currently being rendered.

This works because the set of views returned by an [`XRViewerPose`](../xrviewerpose) each represent one eye's perspective on the scene. Since the framebuffer is split in half, one half for each eye, setting the WebGL viewport to match the WebXR layer's viewport will ensure that when rendering the scene for the current eye's pose, it is rendered into the correct half of the framebuffer.

**&lt;&lt;&lt;--- add link to appropriate section in the Cameras and views article ---&gt;&gt;&gt;**

    function drawFrame(time, frame) {
      let session = frame.session;

      let pose = frame.getViewerPose(mainReferenceSpace);

      if (pose) {
        let glLayer = session.renderState.baseLayer;
        gl.bindFramebuffer(gl.FRAMEBUFFER, glLayer.framebuffer);

        gl.clearColor(0, 0, 0, 1.0);
        gl.clearDepth(1.0);
        gl.clear(gl.COLOR_BUFFER_BIT, gl.DEPTH_COLOR_BIT);

        for (let view of pose.views) {
          let viewport = glLayer.getViewport(view);
          gl.viewport(viewport.x, viewport.y, viewport.width, viewport.height);

          /* Render the scene now */
      }
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrwebgllayer-getviewport">WebXR Device API<br />
<span class="small">The definition of 'XRWebGLLayer.getViewport()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

See also
--------

-   [WebXR Device API](../webxr_device_api)
-   <span class="page-not-created">`WebGLLayerInit`</span>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRWebGLLayer/getViewport" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRWebGLLayer/getViewport</a>
