XRReferenceSpaceEvent.transform
===============================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The read-only [`XRReferenceSpaceEvent`](../xrreferencespaceevent) property `transform` indicates the position and orientation of the affected [`referenceSpace`](referencespace)'s native origin after the changes the event represents are applied. The `transform` is defined using the old coordinate system, which allows it to be used to convert coordinates from the pre-event coordinate system to the post-event coordiante system.

Syntax
------

    let refSpace = xrReferenceSpaceEvent.transform;

### Value

An [`XRRigidTransform`](../xrrigidtransform) object providing a transform that can be used to convert coordinates from the pre-event coordinate system to the post-event coordinate system.

Usage notes
-----------

Upon receiving a `reset` event, you can apply the `transform` to cached position or orientation information to shift them into the updated coordinate system. Alternatively, you can just discard any cached positional information and recompute from scratch. The approach you take will depend on your needs.

For details on what causes a `reset` event and how to respond, see the <span class="page-not-created">`reset`</span> event's documentation.

Examples
--------

This example handles the `reset` event by walking through all the objects in a scene, updating each object's position by multiplying it with the event's given `transform`. The scene is represented by a `scene` object, with all the objects in an array called `objects` within it.

    xrReferenceSpace.addEventListener("reset", event => {
      for (let obj of scene.objects) {
        mat4.multiply(obj.transform, obj.transform, event.transform);
      }
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrreferencespaceevent-transform">WebXR Device API<br />
<span class="small">The definition of 'XRReferenceSpaceEvent.transform' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRReferenceSpaceEvent/transform" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRReferenceSpaceEvent/transform</a>
