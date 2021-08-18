XRFrame
=======

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Draft**

This page is not complete.

A [WebXR Device API](webxr_device_api) `XRFrame` object is passed into the [`requestAnimationFrame()`](xrsession/requestanimationframe) callback function and provides access to the information needed in order to render a single frame of animation for an [`XRSession`](xrsession) describing a VR or AR sccene. Events which communicate the tracking state of objects also provide an `XRFrame` reference as part of their structure.

In addition to providing a reference to the [`XRSession`](xrsession) for which this frame is to be rendered, the [`getViewerPose()`](xrframe/getviewerpose) method is provided to obtain the [`XRViewerPose`](xrviewerpose) describing the viewer's position and orientation in space, and [`getPose()`](xrframe/getpose) can be used to create an [`XRPose`](xrpose) describing the relative position of one [`XRSpace`](xrspace) relative to another.

Properties
----------

 [`session`](xrframe/session) <span class="badge inline readonly">Read only </span>   
The [`XRSession`](xrsession) that for which this `XRFrame` describes the tracking details for all objects. The information about a specific object can be obtained by calling one of the methods on the object.

Methods
-------

[`getPose()`](xrframe/getpose)  
Returns an [`XRPose`](xrpose) object representing the spatial relationship between the two specified [`XRSpace`](xrspace) objects.

[`getViewerPose()`](xrframe/getviewerpose)  
Returns an [`XRViewerPose`](xrviewerpose) describing the viewer's position and orientation in a given [`XRReferenceSpace`](xrreferencespace).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#xrframe-interface">WebXR Device API<br />
<span class="small">The definition of 'XRFrame' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`XRFrame`

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

`createAnchor`

85

85

No

No

No

No

No

85

No

No

No

No

`getHitTestResults`

81

81

No

No

No

No

No

81

No

No

No

13.0

`getHitTestResultsForTransientInput`

81

81

No

No

No

No

No

81

No

No

No

13.0

`getPose`

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

`getViewerPose`

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

`session`

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

`trackedAnchors`

85

85

No

No

No

No

No

85

No

No

No

No

See also
--------

-   [WebXR Device API](webxr_device_api)
-   [Spatial tracking in WebXR](webxr_device_api/spatial_tracking)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRFrame" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRFrame</a>
