XRViewerPose
============

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The WebXR Device API interface `XRViewerPose` represents the pose (the position and orientation) of a viewer's point of view on the scene. Each `XRViewerPose` can have multiple views to represent, for example, the slight separation between the left and right eye. This view can represent anything from the point-of-view of a user's XR headset to the viewpoint represented by a player's movement of an avatar using mouse and keyboard, presented on the screen, to a virtual camera capturing the scene for a spectator.

Properties
----------

*In addition to the properties inherited from [`XRPose`](xrpose), `XRViewerPose` includes the following:*

 [`views`](xrviewerpose/views) <span class="badge inline readonly">Read only </span>   
An array of [`XRView`](xrview) objects, one for each viewpoint on the scene which is needed to represent the scene to the user. A typical headset provides a viewer pose with two views whose [`eye`](xrview/eye) property is either `left` or `right`, indicating which eye that view represents. Taken together, these views can reproduce the 3D effect when displayed on the XR device.

Usage notes
-----------

The `XRViewerPose` object is used to describe the state of a viewer of a WebXR scene as it's tracked by the user's XR hardware. The viewer may be the virtual representation of the user, or it may represent another device or interface which may serve as the source of a position and orientation that make up a view upon the scene. For example, every player in a MMORPG might have an instance of `XRViewerPose` to provide a way to calculate what they can see; if the game provides a mechanism that tells the player if another player sees them, or that they see another player, this information becomes crucial.

An `XRViewerPose` is always obtained and referenced relative to an existing [`XRReferenceSpace`](xrreferencespace). This ensures that positions and orientations are reported using the expected relative coordinate system.

To render a scene using the `XRViewerPose` representing the user's head, one would iterate over the views in the [`views`](xrviewerpose/views) array, rendering them one after another. By calling [`viewport()`](webglrenderingcontext/viewport) on the WebGL context, specifying the `XRView` as input, you can get the viewport to use when rendering in order to draw the frame for that eye into the correct part of the drawing surface.

Also, when rendering the scene for spectators or other players in a multiplayer game, the [`transform`](xrpose/transform) of the `XRViewerPose` can be used to determine both placement and facing direction of the other players in the game, so that they can be drawn in the correct place with the correct facing.

The viewer's pose for the animation frame represented by [`XRFrame`](xrframe) can be obtained by calling the frame's [`getViewerPose()`](xrframe/getviewerpose) method, specifying the reference space in which the origin's position should be computed. The returned `XRViewerPose` tells you where the viewer is and what direction they're facing at the time at which the frame takes place.

Examples
--------

In this example—part of the code to render an [`XRFrame`](xrframe), `getViewerPose()` is called to get an `XRViewerPose` using the same reference space the code is using as its base reference space. If a valid pose is returned, the frame is rendered by clearing the backbuffer and then rendering each of the views in the pose; these are most likely the views for the left and right eyes.

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

Passing each `view` to [`getViewport()`](xrwebgllayer/getviewport) returns the WebGL viewport to apply in order to cause the rendered output to be positioned correctly in the framebuffer for renderijng to the corresponding eye on the output device.

This code is derived from [Drawing a frame](#) in [Movement, orientation, and motion: A WebXR example](webxr_device_api/movement_and_motion). You can see more context and see much more on that page.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#xrviewerpose-interface">WebXR Device API<br />
<span class="small">The definition of 'XRViewerPose' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`XRViewerPose`

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

-   [WebXR Device API](webxr_device_api)
-   [Movement, orientation, and motion](webxr_device_api/movement_and_motion)
-   [`XRPose`](xrpose) and [`XRView`](xrview)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRViewerPose" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRViewerPose</a>