XRReferenceSpaceEventInit.transform
===================================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The [`XRReferenceSpaceEventInit`](../xrreferencespaceeventinit) property `transform` indicates the position and orientation of the affected reference space's native origin after the changes the event represents are applied. The `transform` is defined using the old coordinate system, which allows it to be used to convert coordinates from the pre-event coordinate system to the post-event coordiante system.

Syntax
------

    let eventInitDict = {
      referenceSpace: xrReferenceSpace,
      transform: xrRigidTransform
    });

### Value

An [`XRRigidTransform`](../xrrigidtransform) object providing a transform that can be used to convert coordinates from the pre-event coordinate system to the post-event coordinate system.

Examples
--------

This simple snippet calls the constructor to create a new reference space event of type [`reset`](../xrreferencespace/reset_event).

    let refSpaceEvent = new XRReferenceSpaceEvent("reset", {
          referenceSpace: myRefSpace,
          transform: myTransform
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrreferencespaceeventinit-transform">WebXR Device API<br />
<span class="small">The definition of 'XRReferenceSpaceEventInit.transform' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.XRReferenceSpaceEventInit.transform`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRReferenceSpaceEventInit/transform" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRReferenceSpaceEventInit/transform</a>
