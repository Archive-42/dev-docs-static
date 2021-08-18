XRReferenceSpaceEventInit.referenceSpace
========================================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The [`XRReferenceSpaceEventInit`](../xrreferencespaceeventinit) property `referenceSpace` is used to establish the value of a newly-constructed [`XRReferenceSpaceEvent`](../xrreferencespaceevent) object when calling the [`XRReferenceSpaceEvent()`](../xrreferencespaceevent/xrreferencespaceevent) constructor.

Syntax
------

    let eventInitDict = {
      referenceSpace: xrReferenceSpace,
      transform: xrRigidTransform
    });

### Value

An [`XRReferenceSpace`](../xrreferencespace) indicating the source of the event.

Examples
--------

This simple snippet calls the constructor to create a new reference space event of type [`reset`](../xrreferencespace/reset_event).

    let refSpaceEvent = new XRReferenceSpaceEvent("reset", {
          referenceSpace: myRefSpace,
          transform: myTransform
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrreferencespaceeventinit-referencespace">WebXR Device API<br />
<span class="small">The definition of 'XRReferenceSpaceEventInit.referenceSpace' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.XRReferenceSpaceEventInit.referenceSpace`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRReferenceSpaceEventInit/referenceSpace" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRReferenceSpaceEventInit/referenceSpace</a>
