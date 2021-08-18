XRReferenceSpaceEvent
=====================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The [WebXR Device API](webxr_device_api) interface `XRReferenceSpaceEvent` represents an event sent to an [`XRReferenceSpace`](xrreferencespace). Currently, the only event that uses this type is the [`reset`](xrreferencespace/reset_event) event.

Constructor
-----------

[`XRReferenceSpaceEvent()`](xrreferencespaceevent/xrreferencespaceevent)  
Returns a new `XRReferenceSpaceEvent` with the specified type and configured using the values in the given [`XRReferenceSpaceEventInit`](xrreferencespaceeventinit) dictionary.

Properties
----------

*In addition to inheriting the properties available on the parent interface, [`Event`](event), `XRReferenceSpaceEvent` objects include the following properties:*

 [`referenceSpace`](xrreferencespaceevent/referencespace) <span class="badge inline readonly">Read only </span>   
An [`XRReferenceSpace`](xrreferencespace) indicating the reference space that generated the event.

 [`transform`](xrreferencespaceevent/transform) <span class="badge inline readonly">Read only </span>   
An [`XRRigidTransform`](xrrigidtransform) object indicating the position and orientation of the specified `referenceSpace`'s native origin after the event, defined relative to the coordinate system before the event.

Methods
-------

*While `XRReferenceSpaceEvent` does not define any methods, it inherits the methods of its parent interface, [`Event`](event).*

Event types
-----------

[`reset`](xrreferencespace/reset_event)  
The `reset` event is sent to a reference space when its native origin is changed due to a discontinuity, recalibration, or device reset. This is an opportunity for your app to update any stored transforms, position/orientation information, or the like—or to dump any cached values based on the reference's space's origin so you can recompute them as needed.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#xrreferencespaceevent">WebXR Device API<br />
<span class="small">The definition of 'XRReferenceSpaceEvent' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`XRReferenceSpaceEvent`

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

`XRReferenceSpaceEvent`

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

`referenceSpace`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRReferenceSpaceEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRReferenceSpaceEvent</a>
