XRViewerPose.views
==================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The read-only [`XRViewerPose`](../xrviewerpose) property `views` returns an array which contains every [`XRView`](../xrview) which must be rendered in order to fully represent the scene from the viewpoint defined by the viewer pose. For monoscopic devices, this array contains a single view.

**Important:** There is no guarantee that the number of views will remain constant over the lifetime of an [`XRSession`](../xrsession). For each frame, you should always use the current length of this array rather than caching the value.

Stereo views require two views to render properly, with the left eye's view having its [`eye`](../xrview/eye) set to the string `left` and the right eye's view a value of `right`.

Syntax
------

    let viewList = xrViewerPose.views;

### Value

An array of [`XRView`](../xrview) objects, one for each view available as part of the scene for the current viewer pose. This array's length may potentially vary over the lifetime of the [`XRSession`](../xrsession) (for example, if the viewer enables or disables stereo mode on their XR output device).

Examples
--------

In this example—part of the code to render an [`XRFrame`](../xrframe), `getViewerPose()` is called to get an `XRViewerPose` using the same reference space the code is using as its base reference space. If a valid pose is returned, the frame is rendered by clearing the backbuffer and then rendering each of the views in the pose; these are most likely the views for the left and right eyes.

    let pose = frame.getViewerPose(xrReferenceSpace);

    if (pose) {
      let glLayer = xrSession.renderState.baseLayer;

      gl.bindFrameBuffer(gl.FRAMEBUFFER, glLayer.framebuffer);
      gl.clearColor(0, 0, 0, 1);
      gl.clearDepth(1);
      gl.clear(gl.COLOR_BUFFER_BIT, gl.DEPTH_BUFFER_BIT);

      for (let view of pose.views) {
        let viewport = glLayer.getViewport(view);
        gl.viewport(viewport.x, viewport.y, viewport.width, viewport.height);

        /* render the scene for the eye view.eye */
      }
    }

Passing each `view` to [`getViewport()`](../xrwebgllayer/getviewport) returns the WebGL viewport to apply in order to cause the rendered output to be positioned correctly in the framebuffer for renderijng to the corresponding eye on the output device.

This code is derived from [Drawing a frame](#) in [Movement, orientation, and motion: A WebXR example](../webxr_device_api/movement_and_motion). You can see more context and see much more on that page.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrviewerpose-views">WebXR Device API<br />
<span class="small">The definition of 'XRViewerPose.views' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`views`

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
-   [Movement, orientation, and motion](../webxr_device_api/movement_and_motion)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRViewerPose/views" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRViewerPose/views</a>
