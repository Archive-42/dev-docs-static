XRView
======

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The [WebXR Device API](webxr_device_api)'s `XRView` interface provides information describing a single view into the XR scene for a specific frame, providing orientation and position information for the viewpoint. You can think of it as a description of a specific eye or camera and how it views the world. A 3D frame will involve two views, one for each eye, separated by an appropriate distance which approximates the distance between the viewer's eyes. This allows the two views, when projected in isolation into the appropriate eyes, to simulate a 3D world.

Properties
----------

 [`eye`](xrview/eye) <span class="badge inline readonly">Read only </span>   
Which of the two eyes (`left`) or (`right`) for which this `XRView` represents the perspective. This value is used to ensure that any content which is pre-rendered for presenting to a specific eye is distributed or positioned correctly. The value can also be `none` if the `XRView` is presenting monoscopic data (such as a 2D image, a full-screen view of text. or a close-up view of something that doesn't need to appear in 3D).

 [`projectionMatrix`](xrview/projectionmatrix) <span class="badge inline readonly">Read only </span>   
The projection matrix that will transform the scene to appear correctly given the point-of-view indicated by `eye`. This matrix should be used directly in order to avoid presentation distortions that may lead to potentially serious user discomfort.

 [`transform`](xrview/transform) <span class="badge inline readonly">Read only </span>   
An [`XRRigidTransform`](xrrigidtransform) which describes the current position and orientation of the viewpoint in relation to the [`XRReferenceSpace`](xrreferencespace) specified when [`getViewerPose()`](xrframe/getviewerpose) was called on the [`XRFrame`](xrframe) being rendered.

Usage notes
-----------

### Positions and number of XRViews per frame

While rendering a scene, the set of views that are used to render the scene for the viewer as of the current frame are obtained by calling the [`XRFrame`](xrframe) object's [`getViewerPose()`](xrframe/getviewerpose) method to get the [`XRViewerPose`](xrviewerpose) representing (in essence) the position of the viewer's head. That object's [`views`](xrviewerpose/views) property is a list of all of the `XRView` objects representing the viewpoints which can be used to construct the scene for presentation to the user.

It's possible to have `XRView` objects which represent overlapping regions as well as entirely disparate regions; in a game, you might have views that can be presented to observe a remote site using a security camera or other device, for example. In other words, don't assume there are exactly two views on a given viewer; there can be as few as one (such as when rendering the scene in `inline` mode, and potentially many (especially if the field of view is very large). There might also be views representing observers watching the action, or other viewspoints not direclty associated with a player's eye.

In addition, the number of views can change at any time, depending on the needs of the time. So you should process the view list every time without making assumptions based on previous frames.

All positions and orientations within the views for a given [`XRViewerPose`](xrviewerpose) are specified in the reference space that was passed to [`XRFrame.getViewerPose()`](xrframe/getviewerpose); this is called the **viewer reference space**. The [`transform`](xrview/transform) property describes the position and orientation of the eye or camera represented by the `XRView`, given in that reference space.

### The destination rendering layer

To render a frame, you just iterate over the `XRViewerPose`'s views, rendering each of them into the appropriate viewport within the frame's [`XRWebGLLayer`](xrwebgllayer). Currently, the specification (and therefore all current implementations of WebXR) is designed around rendering every `XRView` into a single `XRWebGLLayer`, which is then presented on the XR device with half used for the left eye and half for the right eye. The [`XRViewport`](xrviewport) for each view is used to position the rendering into the correct half of the layer.

If in the future it becomes possible for each view to render into a different layer, there would have to be changes made to the API, so it's safe for now to assume that all views will render into the same layer.

Examples
--------

### Preparing to render every view for a pose

To draw eerything the user sees each frame requires iterating over the list of views returned by the [`XRViewerPose`](xrviewerpose) object's [`views`](xrviewerpose/views) list:

    for (let view of pose.views) {
      let viewport = glLayer.getViewport(view);

      gl.viewport(viewport.x, viewport.y, viewport.width, viewport.height);

      // Draw the scene; the eye being drawn is identified
      // by view.eye.
    }

### Special view transforms

There are a few special transforms that are used on the view while rendering and lighting a scene.

#### Model view matrix

The **model view matrix** is a matrix which defines the position of an object relative to the space in which it's located: If `objectMatrix` is a transform applied to the object to provide its basic position and rotation, then the model view matrix can be computed by multiplying the object's matrix by the inverse of the view transform matrix, like this:

    mat4.multiply(modelViewMatrix, view.transform.inverse.matrix, objectMatrix);

#### Normal matrix

The model view's **normal matrix** is used when lighting the scene, in order to transform each surface's normal vectors to ensure that the light is reflected in the correct direction given the orientation and position of the surface relative to the light source or sources. It's computed by inverting then transposing the model view matrix:

    mat4.invert(normalMatrix, modelViewMatrix);
    mat4.transpose(normalMatrix, normalMatrix);

### Teleporting an object

To programmatically move and/or rotate (often referred to as **teleporting**) an object, you need to create a new reference space for that object which applies a transform that encapsulates the desired changes. The `createTeleportTransform()` function returns the transform needed to move and rotate an object whose current situation is described by the reference space `refSpace` to a new position and orientation which is computed using previously recorded mouse and keyboard input data which has generated offsets for yaw, pitch, and position along all three axes.

    function applyMouseMovement(refSpace) {
      if (!mouseYaw && !mousePitch && !axialDistance &&
          !transverseDistance && !verticalDistance) {
        return refSpace;
      }

      // Compute the quaternion used to rotate the image based
      // on the pitch and yaw.

      quat.identity(inverseOrientation);
      quat.rotateX(inverseOrientation, inverseOrientation, -mousePitch);
      quat.rotateY(inverseOrientation, inverseOrientation, -mouseYaw);

      // Compute the true "up" vector for our object.

      vec3.cross(vecX, vecY, cubeOrientation);
      vec3.cross(vecY, cubeOrientation, vecX);

      // Now compute the transform that teleports the object to the
      // specified point and save a copy of it to display to the user
      // later; otherwise we probably wouldn't need to save mouseMatrix
      // at all.

      let newTransform = new XRRigidTransform({x: transverseDistance,
                                               y: verticalDistance,
                                               z: axialDistance},
                             {x: inverseOrientation[0], y: inverseOrientation[1],
                              z: inverseOrientation[2], w: inverseOrientation[3]});
      mat4.copy(mouseMatrix, newTransform.matrix);

      // Create a new reference space that transforms the object to the new
      // position and orientation, returning the new reference space.

      return refSpace.getOffsetReferenceSpace(newTransform);
    }

This code is broken into four sections. In the first, the quaternion `inverseOrientation` is computed. This represents the rotation of the object given the values of `mousePitch` (rotation around the object's reference's space's X axis) and `mouseYaw` (rotation around the object's Y axis).

The second section computes the "up" vector for the object. This vector indicates the direction which is "up" in the scene overall, but in the object's reference space.

The third section creates the new [`XRRigidTransform`](xrrigidtransform), specifying a point providing the offsets along the three axes as the first parameter, and the orientation quaternion as the second parameter. The returned object's [`matrix`](xrrigidtransform/matrix) property is the actual matrix that transforms points from the scene's reference space to the object's new position.

Finally, a new reference space is created to describe the relationship between the two reference spaces fully. That reference space is returned to the caller.

To use this function, we pass the returned reference space into [`XRFrame.getPose()`](xrframe/getpose) or [`getViewerPose()`](xrframe/getviewerpose), as appropriate for your needs. The returned [`XRPose`](xrpose) will then be used to render the scene for the current frame.

You can find a more extensive and complete example in our article [Movement, orientation, and motion](webxr_device_api/movement_and_motion).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#xrview-interface">WebXR Device API<br />
<span class="small">The definition of 'XRView' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`XRView`

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

`eye`

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

`isFirstPersonObserver`

86

86

No

No

No

No

No

86

No

No

No

13.0

`projectionMatrix`

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

`transform`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRView" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRView</a>
