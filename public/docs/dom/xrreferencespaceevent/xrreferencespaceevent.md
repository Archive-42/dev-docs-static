XRReferenceSpaceEvent()
=======================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `XRReferenceSpaceEvent()` constructor is used to create a new [`XRReferenceSpaceEvent`](../xrreferencespaceevent) object, which represents an event regarding the state of a WebXR reference space object, [`XRReferenceSpace`](../xrreferencespace).

Currently, only the [`reset`](../xrreferencespace/reset_event) event is defined using this type.

Syntax
------

    let refSpaceEvent = new XRReferenceSpaceEvent(type, eventInitDict);

### Parameters

`type`  
A [`DOMString`](../domstring) indicating the event type which has occurred. Currently, this is always `reset`.

`eventInitDict`  
An object based on the [`XRReferenceSpaceEventInit`](../xrreferencespaceeventinit) dictionary, containing data used to initialize the new event object. The properties of this object are:

[`referenceSpace`](../xrreferencespaceeventinit/referencespace)  
The [`XRReferenceSpace`](../xrreferencespace) from which the event originated.

[`transform`](../xrreferencespaceeventinit/transform)  
An [`XRRigidTransform`](../xrrigidtransform) which maps the old coordinate system (from before the changes indicated by this event) to the new coordiante system.

### Return value

A new `XRReferenceSpaceEvent` object, initialized as defined by the input parameters.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrreferencespaceevent-xrreferencespaceevent">WebXR Device API<br />
<span class="small">The definition of 'XRReferenceSpaceEvent()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRReferenceSpaceEvent/XRReferenceSpaceEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRReferenceSpaceEvent/XRReferenceSpaceEvent</a>
