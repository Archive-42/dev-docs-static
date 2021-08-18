XRRigidTransform.inverse
========================

The read-only `inverse` property of the [`XRRigidTransform`](../xrrigidtransform) interface returns another [`XRRigidTransform`](../xrrigidtransform) object which is the inverse of its owning transform. That is, you can always get the inverse of any `XRRigidTransform` using its `inverse` property, instead of having to explicitly generate it.

Syntax
------

    let transformInverse = xrRigidTransform.inverse;

### Value

An [`XRRigidTransform`](../xrrigidtransform) which contains the inverse of the `XRRigidTransform` on which it's accessed.

Applying the inverse of a transform to any object previously transformed by the parent `XRRigidTransform` always undoes the transformation, resulting in the object returning to its previous pose. In other words, its position and orientation both return to their prior configurations.

Examples
--------

In this example, the model view matrix for an object is computed by taking the view matrix and multiplying it by the object's pose matrix.

    let modelViewMatrix = mat4.create();

    for (let view of pose.view) {
      let viewport = glLayer.getViewport(view);
      gl.viewport(viewport.x, viewport.y, viewport.width, viewport.height);

      /* ... */

      mat4.multiply(modelViewMatrix, view.transform.inverse.matrix, objectMatrix);
      gl.uniformMatrix4fv(programInfo.uniformLocations.modelViewMatrix,
                          false, modelViewMatrix);

      /* ... */
    }

This outline of a renderer's core code shows how the pose's view gets represented by taking its transform's inverse's matrix as the model view matrix used to transform objects based on the viewer's position and orientation. The inverse's matrix is multiplied by the object's matrix to get the model view matrix, which is then passed into the shader program by setting a uniform to contain that information.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrrigidtransform-inverse">WebXR Device API<br />
<span class="small">The definition of 'XRRigidTransform.inverse' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`inverse`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRRigidTransform/inverse" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRRigidTransform/inverse</a>
