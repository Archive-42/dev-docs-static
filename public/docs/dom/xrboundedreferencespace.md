XRBoundedReferenceSpace
=======================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The [WebXR Device API](webxr_device_api)'s `XRBoundedReferenceSpace` interface describes a virtual world [reference space](webxr_device_api/geometry) which has preset boundaries. This extends [`XRReferenceSpace`](xrreferencespace), which describes an essentially unrestricted space around the viewer's position. These bounds are defined using an array of points, each of which defines a vertex in a polygon inside which the user is allowed to move.

This is typically used when the XR system is capable of tracking the user's physical movement within a limited distance of their starting position. The specified bounds may, in fact, describe the shape and size of the room the user is located in, in order to let the WebXR site or application prevent the user from colliding with the walls or other obstacles in the real world. At a minimum, the boundaries indicate the area in which the XR device is capable of tracking the user's movement. See the article [Using bounded reference spaces](webxr_device_api/bounded_reference_spaces) for details on how bounded spaces work and why they're useful.

Properties
----------

*In addition to the properties of [`XRReferenceSpace`](xrreferencespace), `XRBoundedReferenceSpace` includes the following:*

 [`boundsGeometry`](xrboundedreferencespace/boundsgeometry) <span class="badge inline readonly">Read only </span>   
An array of [`DOMPointReadOnly`](dompointreadonly) objects, each of which defines a vertex in the polygon defining the boundaries within which the user will be required to remain. These vertices *must* be sorted such that they move *clockwise* around the viewer's position.

Methods
-------

*`XRBoundedReferenceSpace` inherits the methods of its parent interface, [`XRReferenceSpace`](xrreferencespace). It has no further methods.*

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#xrboundedreferencespace-interface">WebXR Device API<br />
<span class="small">The definition of 'XRBoundedReferenceSpace' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`XRBoundedReferenceSpace`

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

`boundsGeometry`

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

See also
--------

-   [WebXR Device API](webxr_device_api)
-   [Geometry and reference spaces in WebXR](webxr_device_api/geometry)
-   [Viewpoints and viewers: simulating cameras in WebXR](webxr_device_api/cameras)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRBoundedReferenceSpace" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRBoundedReferenceSpace</a>
