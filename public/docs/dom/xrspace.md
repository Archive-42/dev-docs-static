XRSpace
=======

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `XRSpace` interface of the [WebXR Device API](webxr_device_api) is an abstract interface providing a common basis for every class which represents a virtual coordinate system within the virtual world, in which its origin corresponds to a physical location. Spatial data in WebXR is always expressed relative to an object based upon one of the descendant interfaces of `XRSpace`, at the time at which a given [`XRFrame`](xrframe) takes place.

Numeric values such as pose positions are thus coordinates in the corresponding `XRSpace`, relative to that space's origin.

**Note:** The `XRSpace` interface is never used directly; instead, all spaces are created using one of the interfaces based on `XRSpace`. At this time, those are [`XRReferenceSpace`](xrreferencespace) and [`XRBoundedReferenceSpace`](xrboundedreferencespace).

Interfaces based on XRSpace
---------------------------

Below is a list of interfaces based on the `XRSpace` interface.

[`XRBoundedReferenceSpace`](xrboundedreferencespace)  
Represents a reference space which may move within a region of space whose borders are defined by an array of points laid out in clockwise order along the floor to define the passable region of the space. The origin of an `XRBoundedReferenceSpace` is always at floor level, with its X and Z coordinates typically defaulting to a location near the room's center.

[`XRReferenceSpace`](xrreferencespace)  
Represents a reference space which is typically expected to remain static for the duration of the [`XRSession`](xrsession). While objects may move within the space, the space itself remains fixed in place. There are exceptions to this static nature; most commonly, an `XRReferenceSpace` may move in order to adjust based on reconfiguration of the user's headset or other motion-sensitive device.

Properties
----------

*The `XRSpace` interface defines no properties of its own; however, it does inherit the properties of its parent interface, [`EventTarget`](eventtarget).*

Methods
-------

*The `XRSpace` interface provides no methods of its own. However, it inherits the methods of [`EventTarget`](eventtarget), its parent interface.*

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#xrspace-interface">WebXR Device API<br />
<span class="small">The definition of 'XRSpace' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`XRSpace`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRSpace" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRSpace</a>
