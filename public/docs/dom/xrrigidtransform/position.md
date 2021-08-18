XRRigidTransform.position
=========================

The read-only [`XRRigidTransform`](../xrrigidtransform) property `position` is a [`DOMPointReadOnly`](../dompointreadonly) object which provides the 3D point, specified in meters, describing the translation component of the transform.

Syntax
------

    let pos = xrRigidTransform.position;

### Value

A read-only [`DOMPointReadOnly`](../dompointreadonly) indicating the 3D position component of the transform matrix. The units are meters.

**Note:** The `w` component of the point is always 1.0.

Example
-------

To create a reference space which can be used to place an object at eye level (assuming eye level is 1.5 meters):

    function onSessionStarted(xrSession) {
      xrSession.addEventListener("end", onSessionEnded);

      gl = initGraphics(xrSession);

      let glLayer = new XRWebGLLayer(xrSession, gl);
      xrSession.updateRenderState({ baseLayer: glLayer });

      if (immersiveSession) {
        xrSession.requestReferenceSpace("bounded-floor").then((refSpace) => {
          refSpaceCreated(refSpace);
        }).catch(() => {
          session.requestReferenceSpace("local-floor").then(refSpaceCreated);
        });
      } else {
        session.requestReferenceSpace("viewer").then(refSpaceCreated);
      }
    }

    function refSpaceCreated(refSpace) {
      if (immersiveSession) {
        xrReferenceSpace = refSpace;
      } else {
        xrReferenceSpace = refSpace.getOffsetReferenceSpace(
          new XRRigidTransform({y: -1.5});
        );
      }
      xrSession.requestAnimationFrame(onFrame);
    }

After setting up the graphics context for WebXR use, this begins by looking to see if a variable `immersiveSession` is `true`; if so, we first request a `bounded-floor` reference space. if that fails (probably because `bounded-floor` isn't supported), we try requesting a `local-floor` reference space.

If we're not in an immersive session, we instead request a `viewer` reference space.

In all cases, once the space has been obtained, it gets passed into the `refSpaceCreated()` function. For immersive spaces, the specified space is saved for future use. However, for inline sesions, we know we're in a space not automatically adjusted for floor level, so we request an offset reference space to shift the viewer's height to 1.5 meters above the presumed floor level of 0 meters. That new reference space is used instead of the one initially received.

Finally, an animation frame request is submitted.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrrigidtransform-position">WebXR Device API<br />
<span class="small">The definition of 'XRRigidTransform.position' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`position`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRRigidTransform/position" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRRigidTransform/position</a>
