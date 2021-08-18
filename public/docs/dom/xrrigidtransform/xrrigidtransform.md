XRRigidTransform()
==================

The **`XRRigidTransform``()`** constructor creates and returns a new [`XRRigidTransform`](../xrrigidtransform) object, representing the position and orientation of a point or object. Among other things, `XRRigidTransform` is used when providing a transform to translate between coordinate systems across spaces.

Syntax
------

    let xrRigidTransform = new XRRigidTransform(position, orientation);

### Parameters

 `position` <span class="badge inline optional">Optional</span>   
An object conforming to [`DOMPointInit`](../dompointinit) which specifies the coordinates at which the point or object is located. These dimensions are specified in meters. If this parameter is left out or is not compatible with `DOMPointInit`, the position used is assumed to be `{x: 0, y: 0, z: 0, w: 1}`. `w` must *always* be 1.

 `orientation` <span class="badge inline optional">Optional</span>   
An object conforming to [`DOMPointInit`](../dompointinit) which specifies the direction in which the object is facing. The default value for `orientation` is `{x: 0, y: 0, z: 0, w: 1}`. The specified orientation gets normalized if it's not already.

### Return value

A new [`XRRigidTransform`](../xrrigidtransform) object which has been initialized to represent a transform matrix that would adjust the position and orientation of an object from the origin to the specified `position` and facing in the direction indicated by `orientation`.

### Exceptions

`TypeError`  
The value of the `w` coordinate in the specified `position` is not 1.0.

Examples
--------

In this example, the beginning of the animation of a scene is shown, starting with a request for a reference space of a given type, then shifting the coordinate system based on a transform before requesting the first animation frame.

    let animationFrameRequestID = 0;

    xrSession.requestReferenceSpace("local-floor")
    .then((refSpace) => {
      xrReferenceSpace = refSpace.getOffsetReferenceSpace(
            new XRRigidTransform(viewerPosition, viewerOrientation));
      animationFrameRequestID = xrSession.requestAnimationFrame(drawFrame);
    });

After requesting a reference space of type `local-floor`, the returned promise is eventually resolved, at which time we receive a new reference space object, `refSpace`. After creating an `XRRigidTransform` from the viewer's initial position and orientation, we pass the new transform into [`getOffsetReferenceSpace()`](../xrreferencespace/getoffsetreferencespace) to create *another* reference space, now offset so that its origin is located at the same place in space as the coordinates given by `viewerPosition`, with the orientation also revised in the same fashion.

Then [`requestAnimationFrame()`](../xrsession/requestanimationframe) is called to ask for a new animation frame to draw into. The `drawFrame()` callback will be executed when the system is ready to draw the next frame.

You can find more examples in [Movement, orientation, and motion](../webxr_device_api/movement_and_motion).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrrigidtransform-xrrigidtransform">WebXR Device API<br />
<span class="small">The definition of 'XRRigidTransform()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`XRRigidTransform`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRRigidTransform/XRRigidTransform" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRRigidTransform/XRRigidTransform</a>
