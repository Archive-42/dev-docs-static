XRReferenceSpaceEventInit
=========================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `XRReferenceSpaceEventInit` dictionary is used when calling the [`XRReferenceSpaceEvent()`](xrreferencespaceevent/xrreferencespaceevent) constructor to provide the values for its properties. Since the properties are read-only, this is the only opportunity available to set their values.

You will not usually need to use this, since these events are created by the WebXR infrastructure.

Properties
----------

[`referenceSpace`](xrreferencespaceeventinit/referencespace)  
The [`XRReferenceSpace`](xrreferencespace) from which the event originated.

[`transform`](xrreferencespaceeventinit/transform)  
An [`XRRigidTransform`](xrrigidtransform) which maps the old coordinate system (from before the changes indicated by this event) to the new coordiante system.

Usage notes
-----------

All of this dictionary's properties must have valid values set on them before calling the [`XRReferenceSpaceEvent()`](xrreferencespaceevent/xrreferencespaceevent) constructor.

Examples
--------

This simple snippet calls the constructor to create a new reference space event of type [`reset`](xrreferencespace/reset_event).

    let refSpaceEvent = new XRReferenceSpaceEvent("reset", {
          referenceSpace: myRefSpace,
          transform: myTransform
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dictdef-xrreferencespaceeventinit">WebXR Device API<br />
<span class="small">The definition of 'XRReferenceSpaceEventInit' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.XRReferenceSpaceEventInit`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRReferenceSpaceEventInit" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRReferenceSpaceEventInit</a>
