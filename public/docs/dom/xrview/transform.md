XRView.transform
================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Draft**

This page is not complete.

The read-only `transform` property of the [`XRView`](../xrview) interface is an [`XRRigidTransform`](../xrrigidtransform) object which provides the position and orientation of the viewpoint relative to the [`XRReferenceSpace`](../xrreferencespace) specified when the [`XRFrame.getViewerPose()`](../xrframe/getviewerpose) method was called to obtain the view object.

With the `transform`, you can then position the view as a camera within the 3D scene. If you instead need the more traditional view matrix, you can get using `view.transform.inverse.matrix`; this gets the underlying [`matrix`](../xrrigidtransform/matrix) of the transform's [`inverse`](../xrrigidtransform/inverse).

Syntax
------

    let viewTransform = xrView.transform;

### Value

A [`XRRigidTransform`](../xrrigidtransform) object specifying the position and orientation of the viewpoint represented by the `XRView`.

Examples
--------

For each view making up the presented scene, the view's `transform` represents the position and orientation of the viewer or camera relative to the reference space's origin. You can then use the inverse of this matrix to transform the objects in your scene to adjust their placement and orientation to simulate the viewer's movement through space.

In this example, we see an outline of a code fragment used while rendering an [`XRFrame`](../xrframe), which makes use of the view transform to place objects in the world during rendering.

    const modelViewMatrix = mat4.create();
    const normalMatrix = mat4.create();

    for (let view of pose.views) {
      let viewport = glLayer.getViewport(view);
      gl.viewport(viewport.x, viewport.y, viewport.width, viewport.height);

      for (let obj of world.objects) {
        mat4.multiply(modelViewMatrix, view.transform.inverse.matrix, obj.matrix);
        mat4.invert(normalMatrix, modelViewMatrix);
        mat4.transpose(normalMatrix, normalMatrix);

        obj.render(modelViewMatrix, normalMatrix);
      }
    }

Two matrices are created outside the rendering loop; this avoids repeatedly allocating and deallocating the matrices, and generally reduces overhead by reusing the same matrix for each object rendered.

Then we iterate over each [`XRView`](../xrview) found in the [`XRViewerPose`](../xrviewerpose)'s list of [`views`](../xrviewerpose/views). There will usually be two: one for the left eye and one for the right, but there may be only one if in monoscopic mode. Currently, WebXR doesn't support more than two views per pose, although room has been left to extend the specification to support that in the future with some additions to the API.

For each view, we obtain its viewport and pass that to WebGL using [`gl.viewport()`](../webglrenderingcontext/viewport). For the left eye, this will be the left half of the canvas, while the right eye will use the right half.

Then we iterate over each object that makes up the scene. Each object's model view matrix is computed by multiplying its own matrix which describes the object's own position and orientation by the additional position and orientation adjustments needed to match the camera's movement. To convert the "camera focused" transform matrix into an "object focused" transform, we use the transform's inverse, thus taking the matrix returned by [`view.transform.inverse.matrix`](../xrrigidtransform/matrix). The resulting model view matrix will apply all the transforms needed to move and rotate the object based on the relative positions of the object and the camera. This will simulate the movement of the camera even though we're actually moving the object.

We then compute the normals for the model view matrix by inverting it, then transposing it.

Finally, we call the object's `render()` routine, passing along the `modelViewMatrix` and `normalMatrix` so the renderer can place and light the object properly.

**Note:** This example is derived from a larger example... **&lt;&lt;&lt;--- finish and add link ---&gt;&gt;&gt;**

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrview-transform">WebXR Device API<br />
<span class="small">The definition of 'XRView.transform' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRView/transform" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRView/transform</a>
